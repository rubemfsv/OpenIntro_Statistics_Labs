# Lab 6: Inference for Categorical Data

## Sua Vez
### 1
#### a

spain05 <- subset(atheism, nationality == "Spain" & year == "2005")

spain12 <- subset(atheism, nationality == "Spain" & year == "2012")

inference(spain05$response, est = "proportion", type = "ci", method = "theoretical", success = "atheist", conf = 0.95)

H0: Na Espanha não tem diferença entre a proporção de ateus em 2005 e 2012.

HA: Na Espanha tem uma diferença entre a proporção de ateus em 2005 e 2012.

Temos duas condições, a primeira é que as observações são independentes em cada amostra e entre as amostras, e, assumimos que seja sim. Após isso, tem a condição de sucesso / falha satisfeita para ambas as amostras tendo pelo menos 10 de cada sucesso e falha, porém, a função de inferência verifica isso, sua saída está abaixo, e sim, portanto, as condições são atendidas, sendo todos os grupos maiores que 10 observações.

Os intervalos de confiança se sobrepõem, portanto não há evidência convincente para rejeitar a hipótese nula. 

A proporção de ateus na Espanha não teve uma mudança significativa em seus índices no nível de confiança de 95% entre os anos de 2005 e 2012.

#### b

load("atheism.RData")

us05 <- subset(atheism, nationality == "United States" & year == "2005")

us12 <- subset(atheism, nationality == "United States" & year == "2012")

inference(us05$response, est = "proportion", type = "ci", method = "theoretical", success = "atheist", conf = 0.95)

Usando as mesmas condições e hipóteses do item acima, mas substituindo '"Spain" por "United States".

Os intervalos de confiança não se sobrepõem, portanto, há evidência que nos permite jogar fora a hipótese nula.

Concluímos que a proporção de ateus dos Estados Unidos mudou significativamente no nível de confiança de 95% entre os anos de 2005 e 2012.

### 2

De acordo com o livro texto, um erro de tipo 1 ocorre quando rejeitamos incorretamente a hipótese nula em favor de uma alternativa. Se usarmos um nível de significância de 5% (tendo o nível de confiança com o valor de 95%), fazemos alguns erros de tipo 1 em 5% do tempo. No entanto, se todos os países listados na tabela 4 não tiverem uma mudança real, então, usando nossos dados amostrais, vamos encontrar provavelmente cerca de 5% deles que indicam uma diferença no nível de significância de 5%. Esta pergunta supõe que todos os países não têm diferença real e os nossos dados indicam que 5% têm uma diferença, estes 5% constituiriam, então, um erro de tipo 1, ou seja, os dados nos levam a crer que havia uma diferença quando não havia uma real diferença.

### 3

Vamos calcular o número n de observações que são necessárias para garantir que a margem de erro (ME) seja ≤ 0,01.

A margem de erro é igual a: ME = z* EP,

Sendo EP é o erro padrão da proporção média de amostragem e definido por EP = sqrt( p (p - 1) / n). 

Então, substituindo o valor de EP na fórmula da margem de erro, temos ME = z* sqrt(p (p - 1) / n).

Agora, notamos que n aparece na equação. Reorganizando, temos:

I. ME / z* = sqrt( p (p - 1) / n )

II. (ME / z*) ^ 2 = p (p - 1) / n

III. (ME / z*) ^ 2 / (p (p - 1)) = 1/ n

IV. n = p (p - 1) / (ME / z*) ^ 2

Observamos então que n depende de p, ME e z*, ou seja, para encontrarmos o valor de n, precisamos dos valores dos outros elementos. Sabemos que z* é 1.96 quando é dado o nível de confiança de 95%, e a margem de erro é 1% (0.01), porém, não é conhecido o valor da proporção da população.

Nós usaríamos uma estimativa que fosse ao menos razoavelmente confiante se tivéssemos, porém, não temos. No entanto, foram dadas instruções para garantir que a margem de erro não fosse maior que 1%, e já que não temos nenhuma estimativa, queremos assumir um valor para p que leva à maior margem de erro, para o pior caso, para que a gente nunca conseguir possivelmente ultrapassar o valor de 1%, não importando qual seja o p real seja escolhido.

Com essa informação, buscando no livro e no exercício 8 desse laboratório, é sabido que quando p tem o valor de 0.5, a ME é maior. O valor escolhido para p, portanto, é de 0.5 para calcular n.

Substituindo as constantes da equação em IV (n = p (p - 1) / (ME / z*) ^ 2), temos n = (0.5(0.5-1)) / ((0.01 / 1.96) ^ 2), ou seja, n = 9603.99, isso remete que precisamos de 9604 observações para que possamos garantir que nossa margem de erro seja menor ou igual a 1% no nível de confiança de 95%.

### 4

Inferência para uma única proporção, diferença de duas proporções, testes de qualidade usando qui-quadrado, condição de sucesso e fracasso, teste de hipóteses de pequena amostra para uma proporção.
