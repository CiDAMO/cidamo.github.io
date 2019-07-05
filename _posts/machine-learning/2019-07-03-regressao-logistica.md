---
layout: page
#
# Content
#
subheadline: "Introdução à"
title: "Regressão Logística"
teaser: "Neste post iremos ver os conceitos básicos que definem a regressão logística estudando a teoria por trás desse método, mas sem entrar em muito detalhes."
categories:
  - classificação
tags:
  - classificação
  - regressão logística
#
# Styling
#
header: no
image:
    title: 2019-07-03-regressao-logistica-notebook/imagem15.png
    thumb: 2019-07-03-regressao-logistica-notebook/imagem15.png
    homepage: 2019-07-03-regressao-logistica-notebook/imagem15.png
    caption:
    caption_url:
mediaplayer: false
urlimg: 2019-07-03-regressao-logistica-notebook/
---

**Preparando o ambiente**

Utilizaremos a linguagem Julia para desenvolver o método de regressão logística. A primeira coisa a fazer, então, é inicializar o pacote de imagens, e rodar um exemplo simples para fazer a precompilação do pacote.

{% highlight julia %}
using Plots
pyplot(size=(600,400))
plot(rand(10), rand(10))
nothing
{% endhighlight %}

## Introdução

A regressão logística é um método de classificação. No caso mais simples, o problema de classificação consiste em observar um conjunto de indivíduos de uma classe $$A$$ ou $$B$$, e através das características desses indivíduos, decidir a classe de um novo indivíduo. O método de regressão logística utiliza conceitos de regressão para definir um modelo para a probabilidade de estar na classe $$A$$ ou $$B$$. Vamos estudar como chegar nesse ponto olhando para um problema mais simples.

## Cara ou coroa

Lance uma moeda pra cima, desbalanceada. Digamos que existe 30% de cair CARA e 70% de cair COROA. Simulamos abaixo 1000 arremessos dessa moeda:

{% highlight julia %}
using Random

Random.seed!(0) # Garantindo que é reprodutível

arremessos = []
for i = 1:1000
    r = rand()
    if r < 0.3
        push!(arremessos, 0)
    else
        push!(arremessos, 1)
    end
end
scatter(arremessos, ms=2, leg=false)
xlabel!("Arremessos")
yticks!([0,1],["Cara","Coroa"])
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem01.png)

Vejamos o histograma:

{% highlight julia %}
histogram(arremessos, leg=false)
ylims!(0, length(arremessos))
xticks!([0, 1], ["Cara","Coroa"])
yticks!(0:100:1000)
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem02.png)

Como esperado, temos por volta de 300 dos arremessos sendo CARA (0), e por volta de 700 sendo COROA (1).

A função que dá a probabilidade da moeda cair CARA (0) ou COROA (1) é

$$ P(X = x) = p^x(1 - p)^{1-x}, $$

onde $$X$$ é o arremesso e $$x$$ pode ser $$0$$ ou $$1$$. Dizemos que $$X$$ é uma variável com distribuição Bernoulli.

A partir da probabilidade de 30% de CARA, i.e., $$p = 0.7$$, nós simulamos os dados acima. Mas suponha que queremos fazer o caminho inverso: a partir dos dados, qual é a probabilidade de dar CARA ou COROA? Qual o valor de $$p$$?

Veja que neste caso podemos simplesmente calcular a porcentagem de dados, isto é, o número de CARAS pelo número total de arremessos. No entanto, para algumas situações mais complicadas (como veremos em breve), temos outra estratégia.

Vamos chamar de $$X_i$$ o $$i$$-ésimo arremesso. Considerando todos os arremessos independentes, a probabilidade de acontecer esses arremessos $$X_1 = x_1, X_2 = x_2, \dots, X_n = x_n$$, é

$$\begin{align*}
  P(X_1 = x_1, \dots, X_n = x_n) & = P(X_1 = x_1)\cdot\ldots\cdot P(X_n = x_n) \\
  & = \prod_{i = 1}^n P(X_i = x_i) \\
  & = \prod_{i = 1}^n p^{x_i}(1 - p)^{1 - x_i} \\
  & := L(p).
\end{align*}$$

Para deixar mais claro, considere que apenas 5 arremessos foram feitos, e que o resultado foi de quatro caras e de 1 coroa, nessa ordem. Qual a probabilidade disso acontecer para um moeda balanceada? Cada arremesso tem probabilidade 0.5 de acontecer cara ou coroa, então a probabilidade é $$0.5^5 = 0.03125$$. Se, por outro lado, a moeda tivesse um desbalanceamento de 60% de chance de dar cara, a probabilidade desse resultado seria $$0.6^4\times 0.4 = 0.05184$$. Podemos ver que se a moeda é desbalanceada para caras, então a chance de sair um resultado de quatro caras e 1 coroa é maior. Então a função $$L$$ mede quão bem uma moeda com parâmetro $$p$$ explica o evento acima. Nossa pergunta é **qual o parâmetro que melhor explica o evento**, ou seja, que dá o melhor valor para $$L$$.

Vamos tentar fazer o gráfico dessa função:

{% highlight julia %}
L(p) = prod(p^x * (1 - p)^(1 - x) for x = arremessos)
plot(L, 0, 1, c=:blue, lw=2, leg=false)
xlabel!("p")
ylabel!("L(p)")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem03.png)

Infelizmente os valores são da forma $$p^k(1 - p)^{1000 - k}$$, para algum $$k$$, e isso vai pra 0 rapidamente, por exemplo:

{% highlight julia %}
0.7^100 * (1 - 0.7)^100
{% endhighlight %}

    1.6669764843963514e-68

então $$L(p)$$ está muito abaixo da precisão da máquina, e portanto não devemos tentar usar essa função diretamente. Podemos, no entanto, usar o logaritmo dessa função:

$$\begin{align*}
\ell(p) & = \ln L(p) \\
& = \ln \prod_{i = 1}^n p^{x_i} (1 - p)^{1 - x_i} \\
& = \sum_{i = 1}^n \Big(x_i \ln p + (1 - x_i) \ln (1 - p)\Big).
\end{align*}$$

{% highlight julia %}
ℓ(p) = sum(x * log(p) + (1 - x) * log(1 - p) for x = arremessos)
plot(ℓ, 0, 1, c=:blue, lw=2, y=:log, leg=false)
xlabel!("p")
ylabel!("\$\\ell(p)\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem04.png)

Olhando para a imagem de $$\ell(p)$$, podemos ver que a função atinge um máximo próximo do valor $$p = 0.7$$. Em outras palavras, quando $$p = 0.7$$, a probabilidade de se obter a quantidade de CARAS e COROAS que obtivemos é a maior possível. Isto é, o valor de $$p$$ que melhor explique os dados está próximo de $$p = 0.7$$.

{% highlight julia %}
plot(ℓ, 0.65, 0.75, c=:blue, lw=2, y=:log, leg=false)
xlabel!("p")
ylabel!("\$\\ell(p)\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem05.png)

{% highlight julia %}
plot(ℓ, 0.68, 0.7, c=:blue, lw=2, y=:log, leg=false)
xlabel!("p")
ylabel!("\$\\ell(p)\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem06.png)

{% highlight julia %}
plot(ℓ, 0.69, 0.694, c=:blue, lw=2, y=:log, leg=false)
xlabel!("p")
ylabel!("\$\\ell(p)\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem07.png)

Fazendo o zoom, verificamos que o valor de $$p$$ está bastante próximo de 0.692. Vejamos quanto seria pela técnica tradicional de cálculo de probabilidade:

{% highlight julia %}
count(arremessos .== 1) / length(arremessos)
{% endhighlight %}

    0.692

Por outro lado, vamos olhar para o problema de maximizar $$\ell(p)$$. Derivando e igualando a zero temos

$$\begin{align}
\ell'(p) & = \frac{1}{p}\sum_{i=1}^n x_i - \frac{1}{1 - p}\sum_{i=1}^n(1 - x_i) \\
& = \frac{1}{p(1 - p)}\bigg(\sum_{i = 1}^n x_i - np\bigg).
\end{align}$$

Igualando a zero, obtemos $$p = \frac{1}{n}\sum_{i = 1}^n x_i$$, que é o número de COROAS pelo número de observações.
O nome correto desse processo é estimação por máxima log-verossimilhança.

### (Tópico lateral) A mesma ideia com a distribuição Normal

A ideia acima funciona para outras distribuições também. Vamos ver com a distribuição Normal:

Se $$X$$ é uma distribuição Normal com média $$\mu$$ e variância $$\sigma^2$$, ela tem uma distribuição de probabilidade

$$ f(x) = \frac{1}{\sqrt{2\pi}\sigma} e^{-(x - \mu)^2 / 2\sigma^2}. $$

{% highlight julia %}
using Distributions

μ, σ = 5.67, 0.123
D = Normal(μ, σ)
plot(x -> pdf(D, x), μ - 5σ, μ + 5σ, c=:red, lw=2, leg=false)
xlabel!("x")
ylabel!("Distribuição de probabilidade Normal")
{% endhighlight %}

Tomando uma amostra de tamanho 1000:

![png]({{ site.urlimg }}{{ page.urlimg }}imagem08.png)

{% highlight julia %}
x = rand(Normal(μ, σ), 1000)
scatter(x, leg=false)
xlabel!("índice")
ylabel!("indivíduo")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem09.png)

{% highlight julia %}
histogram(x, leg=false)
xlabel!("x")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem10.png)

Considere essa amostra e suponha que queremos encontrar $$\mu$$ e $$\sigma$$. 
De maneira similar a feita com Bernoulli, definimos a função $$L$$

$$\begin{align}
L(\mu,\sigma) & = f(x_1)f(x_2)\dots f(x_n) = \prod_{i=1}^n f(x_i) \\
& = \frac{1}{\sigma \sqrt{2\pi}} \prod_{i=1}^n e^{-(x_i-\mu)^2/2\sigma^2},
\end{align}$$

e o log dessa função

$$\begin{align}
\ell(\mu,\sigma) & = \ln L(\mu,\sigma) \\
& = -\frac{1}{2\sigma^2} \sum_{i=1}^n (x_i - \mu)^2 - n \ln(\sqrt{2\pi}\sigma).
\end{align}$$

Calculando as derivadas parciais de $$\ell$$ em relação à $$\mu$$ e $$\sigma$$ e igualando a 0, obtemos

$$ \mu = \frac{1}{n}\sum_{i=1}^n x_i $$

e

$$ \sigma^2 = \frac{1}{n}\sum_{i=1}^n (x_i - \mu)^2, $$

que são a média e variância amostrais.

## Agora pra regressão

Suponha agora que temos um conjunto $$\{(x_i, y_i), i = 1,\dots,n\}$$, onde $$x_i$$ é uma variável contínua e $$y_i \in \{0,1\}$$.

Por exemplo, considere uma quantidade $$n$$ de pessoas que pediram empréstimos, cada uma com um salário $$x_i$$, e seja $$y_i$$ se essa pessoa recebeu ($$y_i = 1$$) ou não ($$y_i = 0$$) um empréstimo.

Iremos modelar que para um valor de salário $$x_i$$, a probabilidade de se receber o empréstimo siga uma distribuição Bernoulli com parâmetro $$p_i$$. Se $$Y_i$$ é a variável que indica se a pessoa recebe ou não o empréstimo, então sua probabilidade é dada por

$$ P(Y_i = y_i) = p_i^{y_i} (1 - p_i)^{1 - y_i}. $$

Vamos assumir que existe uma relação entre o valor de $$p_i$$ e o salário $$x_i$$. Inicialmente, poderíamos assumir que $$p_i = \beta_0 + \beta_1 x_i$$, no entanto é fácil ver que essa estratégia leva valores de $$p_i$$ que não são factíveis (fora do intervalo $$[0,1]$$). No lugar, usaremos a relação

$$ p_i = \frac{1}{1 + e^{-\beta_0 - \beta_1 x_i}} = \sigma(\beta_0 + \beta_1 x_i), $$

onde $$\sigma(t) = \dfrac{1}{1 + e^{-t}} = \dfrac{e^t}{1 + e^t}.$$

{% highlight julia %}
plot(t -> 1 / (1 + exp(-t)), -5, 5, c=:black, lw=2, leg=false)
plot!(t -> 1 / (1 + exp(-1 - 2t)), -5, 5, c=:red, lw=1)
plot!(t -> 1 / (1 + exp(1 + 0.4t)), -5, 5, c=:blue, lw=1)
xlabel!("t")
ylabel!("Sigmóides")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem11.png)

Esse modelo se baseia na função de linkagem *logit*, definida por

$$ \text{logit}(p) = \ln\bigg(\frac{p}{1 - p}\bigg), $$

através de $$\text{logit}(p) = \beta_0 + \beta_1 x$$.

Vamos simular esses dados.

{% highlight julia %}
Random.seed!(0)

n = 1000
x = range(1000, 10000, length=n)
β = [-9; 0.002]
y = []
sigmoid(t) = 1 / (1 + exp(-t))
for i = 1:n
    p = sigmoid(β[1] + β[2] * x[i])
    r = rand()
    if r < p
        push!(y, 1)
    else
        push!(y, 0)
    end
end
scatter(x, y, leg=false)
xlabel!("Salário")
yticks!([0,1],["Não", "Sim"])
ylabel!("Recebeu empréstimo")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem12.png)

Aplicando a ideia anterior de maximizar $$\ell(p)$$, obtemos

$$ \max_{\beta} \ \ell(\beta) = \sum_{i = 1}^n y_i \ln(p_i) + (1 - y_i) \ln(1 - p_i). $$

{% highlight julia %}
ℓ(β) = sum(y[i] * log(sigmoid(β[1] + β[2] * x[i])) + (1 - y[i]) * log(1 - sigmoid(β[1] + β[2] * x[i])) for i = 1:n)
contour(range(-20, -5, length=100), range(0, 0.004, length=100), (a,b) -> ℓ([a; b]), levels=100)
xlabel!("\$\\beta_0\$")
ylabel!("\$\\beta_1\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem13.png)

{% highlight julia %}
surface(range(-20, 10, length=40), range(0, 0.004, length=40), (a,b) -> ℓ([a; b]))
xlabel!("\$\\beta_0\$")
ylabel!("\$\\beta_1\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem14.png)

Agora o problema é suficientemente mais difícil.
Para resolvê-lo, utilizaremos os pacotes de otimização do [JuliaSmoothOptimizers](https://juliasmoothoptimizers.github.io/). Em particular, [NLPModels.jl](https://github.com/JuliaSmoothOptimizers/NLPModels.jl) serve para definir o problema de otimização, e [JSOSolvers.jl](https://github.com/JuliaSmoothOptimizers/JSOSolvers.jl) para resolvê-lo.

{% highlight julia %}
using JSOSolvers, NLPModels, Logging

nlp = ADNLPModel(β -> -ℓ(β), zeros(2))
output = with_logger(NullLogger()) do
    lbfgs(nlp)
end
println("β = $(output.solution)")
{% endhighlight %}

    β = [-8.5256, 0.00186498]

{% highlight julia %}
scatter(x, y, leg=false)
ajuste(x) = sigmoid(β[1] + β[2] * x)
modelo(x) = ajuste(x) > 0.5 ? 1 : 0
plot!(ajuste, extrema(x)..., c=:red, lw=2)
plot!(modelo, extrema(x)..., c=:magenta, l=:dash)
xlabel!("Salário")
yticks!([0,1],["Não", "Sim"])
ylabel!("Recebeu empréstimo")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem15.png)

De uma maneira mais geral, se $$x = (1,x^1, x^2, \dots, x^p)$$, podemos fazer o modelo $$p = \sigma(x^T\beta)$$. Abaixo temos um exemplo de duas dimensões:

{% highlight julia %}
Random.seed!(0)
n = 1000
x = rand(n, 2)
y = [max(x[i,1], x[i,2]) > 0.5 + randn() * 0.1 ? 1 : 0 for i = 1:n]
scatter(x[:,1], x[:,2], zcolor=y, c=cgrad([:lightblue,:red]), leg=false)
xlabel!("\$x^1\$")
ylabel!("\$x^2\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem16.png)

{% highlight julia %}
using LinearAlgebra

ϕ(x) = [1.0; x[1]; x[2]]
model(x, β) = sigmoid(dot(β, ϕ(x)))
ℓ(β) = sum(y[i] * log(model(x[i,:], β)) + (1 - y[i]) * log(1 - model(x[i,:], β)) for i = 1:n)

nlp = ADNLPModel(β -> -ℓ(β) + 0.02 * sum(β[j] for j = 2:3)^2, zeros(3)) # Modelo com regularização!
output = with_logger(NullLogger()) do
    lbfgs(nlp)
end
β = output.solution
scatter(x[:,1], x[:,2], zcolor=y, c=cgrad([:lightblue,:red]), leg=false)
contour!(range(extrema(x[:,1])..., length=100), range(extrema(x[:,2])..., length=100), (a,b) -> model([a; b], β), levels=[0.5], lw=2)
xlabel!("\$x^1\$")
ylabel!("\$x^2\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem17.png)

{% highlight julia %}
ϕ(x) = [1.0; x[1]; x[2]; x[1]^2; x[1] * x[2]; x[2]^2]
model(x, β) = sigmoid(dot(β, ϕ(x)))
ℓ(β) = sum(y[i] * log(model(x[i,:], β)) + (1 - y[i]) * log(1 - model(x[i,:], β)) for i = 1:n)

nlp = ADNLPModel(β -> -ℓ(β) + 0.02 * sum(β[j] for j = 2:6)^2, zeros(6)) # Modelo com regularização!
output = with_logger(NullLogger()) do
    lbfgs(nlp)
end
β = output.solution
scatter(x[:,1], x[:,2], zcolor=y, c=cgrad([:lightblue,:red]), leg=false)
contour!(range(extrema(x[:,1])..., length=100), range(extrema(x[:,2])..., length=100), (a,b) -> model([a; b], β), levels=[0.5], lw=2)
xlabel!("\$x^1\$")
ylabel!("\$x^2\$")
{% endhighlight %}

![png]({{ site.urlimg }}{{ page.urlimg }}imagem18.png)

Uma diferença pequena para melhor desempenho do algoritmo foi regularizar o problema, mudando o problema para

$$ \min_{\beta}\ -\ell(\beta) + \lambda \sum_{j=1}^p \beta_j^2. $$

## Resumo

- Ajuste: $$h(x,\beta) = \sigma(x^T\beta)$$;
- Medida: $$\displaystyle \ell(\beta) = \sum_{i = 1}^n y_i \ln \Big(h(x_i,\beta)\Big) + (1 - y_i) \ln \Big(1 - h(x_i,\beta)\Big)$$.
- Modelo: $$m(x) = \left\{\begin{array}{ll} 0, \quad & h(x, \beta) < \tfrac{1}{2}. \\ 1, \quad & h(x, \beta) \geq \tfrac{1}{2}. \end{array}\right.$$
- É um problema de otimização, podemos aplicar
  - Gradiente (usual e estocástico);
  - LBFGS
  - Newton
  - Outros.
