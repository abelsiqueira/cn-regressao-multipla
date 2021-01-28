# Regressão Múltipla

No que vimos de Quadrados Mínimos até agora aprendemos a fazer ajuste de dados do tipo <img src="https://render.githubusercontent.com/render/math?math=\color{cyan}(x_i, y_i), \ i = 1, \dots, n"> por
- Retas;
- Polinômios;
- Modelos lineares mais gerais.
Além disso, em todos esses casos o problema pode ser descrito como

<img src="https://render.githubusercontent.com/render/math?math=\color{cyan}\displaystyle \min_{\beta} \tfrac{1}{2} \Vert X\beta - y\Vert^2,">

com a matriz <img src="https://render.githubusercontent.com/render/math?math=\color{cyan}X"> variando em cada caso. Finalmente, o problema acima é resolvido pelas sistema linear chamada de Equações Normais:

<img src="https://render.githubusercontent.com/render/math?math=\color{cyan}\displaystyle X^T X \beta = X^T y.">

**Retas**

No caso de retas, o modelo é <img src="https://render.githubusercontent.com/render/math?math=\color{cyan} h_{\beta}(x) = \beta_0 %2B \beta_1 x">, a matriz <img src="https://render.githubusercontent.com/render/math?math=\color{cyan}X"> é dada por

<img src="https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bcyan%7D%5Cdisplaystyle%20X%20%3D%20%5Cbegin%7Bbmatrix%7D%201%20%26%20x_1%20%5C%5C%201%20%26%20x_2%20%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%5C%5C%201%20%26%20x_n%20%5Cend%7Bbmatrix%7D.">

**Polinômio**

No caso de polinômios, o modelo é <img src="https://render.githubusercontent.com/render/math?math=\color{cyan} h_{\beta}(x) = \beta_0 %2B \beta_1 x %2B \beta_2 x^2 %2B \dots %2B \beta_p x^p">, a matriz <img src="https://render.githubusercontent.com/render/math?math=\color{cyan}X"> é dada por

<img src="https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bcyan%7D%5Cdisplaystyle%20X%20%3D%20%5Cbegin%7Bbmatrix%7D%201%20%26%20x_1%20%26%20x_1%5E2%20%26%20%5Cdots%20%26%20x_1%5Ep%20%5C%5C%201%20%26%20x_2%20%26%20x_2%5E2%20%26%20%5Cdots%20%26%20x_2%5Ep%20%5C%5C%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cvdots%20%26%20%26%20%5Cvdots%20%5C%5C%201%20%26%20x_n%20%26%20x_n%5E2%20%26%20%5Cdots%20%26%20x_n%5Ep%20%5Cend%7Bbmatrix%7D.">

**Modelo linear geral**

No caso do modelo linear geral, o modelo é <img src="https://render.githubusercontent.com/render/math?math=\color{cyan} h_{\beta}(x) = \beta_1 \phi_1(x) %2B \beta_2 \phi_2(x) %2B \dots %2B \beta_p \phi_p(x)">, a matriz <img src="https://render.githubusercontent.com/render/math?math=\color{cyan}X"> é dada por

<img src="https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bcyan%7DX%20%3D%20%5Cbegin%7Bbmatrix%7D%0A%5Cphi_1(x_1)%20%26%20%5Cphi_2(x_1)%20%26%20%5Cdots%20%26%20%5Cphi_p(x_1)%20%5C%5C%0A%5Cphi_1(x_2)%20%26%20%5Cphi_2(x_2)%20%26%20%5Cdots%20%26%20%5Cphi_p(x_2)%20%5C%5C%0A%5Cvdots%20%26%20%5Cvdots%20%26%20%26%20%5Cvdots%20%5C%5C%0A%5Cphi_1(x_n)%20%26%20%5Cphi_2(x_n)%20%26%20%5Cdots%20%26%20%5Cphi_p(x_n)%20%5C%5C%0A%5Cend%7Bbmatrix%7D.">

## Várias variáveis

Quando queremos encontrar um modelo para prever o valor de <img src="https://render.githubusercontent.com/render/math?math=\color{cyan} y_i"> usando mais de uma variável, fazemos uma coisa muito parecida com o modelo linear geral acima. Por exemplo, se queremos encontrar um modelo de previsão de **salário** com base em informação de **idade**, **anos de experiência** e **anos de estudos**, podemos criar um modelo

<img src="https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bcyan%7D%5Cdisplaystyle%20h_%7B%5Cbeta%7D(x)%20%3D%20%5Cbeta_0%20%2B%20%5Cbeta_%7B%5Ctext%7Bidade%7D%7D%20x%5E%7B%5Ctext%7Bidade%7D%7D%20%2B%20%5Cbeta_%7B%5Ctext%7Banos%20exp%7D%7D%20x%5E%7B%5Ctext%7Banos%20exp%7D%7D%20%2B%20%5Cbeta_%7B%5Ctext%7Banos%20est%7D%7D%20x%5E%7B%5Ctext%7Banos%20est%7D%7D.">

A matriz correspondente será

<img src="https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bcyan%7D%0AX%20%3D%20%5Cbegin%7Bbmatrix%7D%0A1%20%26%20x%5E%7B%5Ctext%7Bidade%7D%7D_1%20%26%20x%5E%7B%5Ctext%7Banos%20exp%7D%7D_1%20%26%20x%5E%7B%5Ctext%7Banos%20est%7D%7D_1%20%5C%5C%0A1%20%26%20x%5E%7B%5Ctext%7Bidade%7D%7D_2%20%26%20x%5E%7B%5Ctext%7Banos%20exp%7D%7D_2%20%26%20x%5E%7B%5Ctext%7Banos%20est%7D%7D_2%20%5C%5C%0A%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cvdots%20%26%20%5Cvdots%20%5C%5C%0A1%20%26%20x%5E%7B%5Ctext%7Bidade%7D%7D_p%20%26%20x%5E%7B%5Ctext%7Banos%20exp%7D%7D_p%20%26%20x%5E%7B%5Ctext%7Banos%20est%7D%7D_p%20%5C%5C%0A%5Cend%7Bbmatrix%7D.">

Simples assim!

Ou seja, montar um modelo é simplesmente ir colocando as colunas que você quer.

## Exercício

Neste exercício temos os dados de um ranqueamento de felicidade de vários países.
Seu objetivo é usar os dados de 2015 a 2018 para escolher os parâmetros de alguns modelo, e usar esse modelo para prever o ranqueamento de felicidade dos países em 2019.

A variável que você deve prever é "Happiness Score", e os modelos que você deve fazer são:

- Um modelo só com a variável "Economy (GDP per Capita)"
- Um modelo só com a variável "Health (Life Expectancy)"
- Um modelo só com a variável "Freedom"
- Um modelo com as 3 variáveis acima
- Um modelo além dos 4 acima mais complexo que os acima que use todas as 3 variáveis, que você deve criar.

**Importante:** Você não pode usar outras variáveis.

### Entregas

- Você deve subir o código que faça a leitura dos dados, cada modelo, as avaliações e os gráficos necessários.
- Você deve subir uma explicação do seu modelo para o GitHub.
- Faça um gráfico mostrando a qualidade do ajuste para cada modelo, tanto para o conjunto 2015 a 2018, quanto para o conjunto 2019.

**Atenção:** Você deve usar apenas os dados de 2015 a 2018 para o treino do modelo. 2019 é usado para validação apenas.

Dicas:
- As colunas extras são irrelevantes mesmo, não tem pegadinha.
- Você pode usar `df = CSV.read("arquivo", DataFrame)
- Você precisa juntar os dados de 2015 a 2018 antes de criar `X` e `y`.