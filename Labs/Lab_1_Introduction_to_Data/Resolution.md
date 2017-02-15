# Lab 1: Introduction to Data

### Exercício 1

source('cdc.R')
dim(cdc)

Com o dim(cdc) temos a resposta, 20000 conjuntos de dados e 9 variáveis. 

genhlth - ordinal 
exerany - ordinal
hlthpln - ordinal
smoke100 - ordinal
height - discreto
weight - discreto 
wtdesire - discreto 
age - discreto 
gender - nominal 

### Exercício 2

Sumário para a altura: summary(cdc$height)
Sumário para a idade: summary(cdc$age)
Intervalo interquartílico para a altura: IQR(cdc$height)
Intervalo interquartílico para a idade: IQR(cdc$age)
Frequência relativa para gender: table(cdc$gender)/nrow(cdc)
Frequência relativa para exerany: table(cdc$exerany)/nrow(cdc)
Número de homens: sum(cdc$gender == 'm')
Proporção da amostra que se diz estar com saúde exelente: sum(cdc$genhlth == 'excellent')/nrow(cdc)

### Exercício 3

Primeiro, faremos o mosaico.

mosaicplot(table(cdc$gender, cdc$smoke100))

Notamos que a proporção de homens que fumaram mais de 100 cigarros  maior que a de mulheres.

### Exercício 4

under23_and_smoke <- subset(cdc, cdc$age < 23 & cdc$smoke100 == 1)

### Exercício 5

imc <- cdc$weight / cdc$height^2 * 703
boxplot(imc ~ cdc$genhlth)

O escolhido foi o exerany por causa da relação de se exercitar com o IMC. 
boxplot(imc ~ cdc$exerany)
Quando exerany é verdadeiro, nota-se que que o IMC  ligeiramente menor.

## Sua Vez
### 1

scatter.smooth(cdc$weight, cdc$wtdesire)

A relação é positiva e linear entre weight e desired weight, quando weight aumenta, desired weight aumenta também.

### 2

cdc$wdiff <- (cdc$wtdesire - cdc$weight)

### 3

O tipo de dado wdiff é uma variável numérica discreta. Se wdiff é positivo, a pessoa deseja pesar mais do que seu peso atual, e, se wdiff é negativo, a pessoa deseja pesar menos do que seu peso atual.

### 4

summary(wdiff)

   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
-300.00  -21.00  -10.00  -14.59    0.00  500.00 

O centro seria a mediana de -10, e a média seria -14.59.

boxplot(wdiff)

plot(table(wdiff[which(wdiff > quantile(wdiff, 0.01) & wdiff < quantile(wdiff, 0.99))]))  

Já aqui, sua forma é unimodal e tem uma inclinação para a esquerda. A partir desses dados, podemos inferir que as pessoas, na maioria, desejam perder peso, enquanto uma parcela pequena deseja se manter no mesmo peso. 

### 5

summary(wdiff[cdc$gender == 'f'])

   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
-300.00  -27.00  -10.00  -18.15    0.00   83.00 

summary(wdiff[cdc$gender == 'm'])

   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
-300.00  -20.00   -5.00  -10.71    0.00  500.00 

boxplot(wdiff ~ cdc$gender, outline=F)

As mulheres normalmente querem que sua diferença entre peso desejado e peso seja mais negativa do que os homens - como também elas têm uma maior disseminação das diferenças desejadas do que os homens.

### 6

mean(cdc$weight)
Média = 169.683

sd(cdc$weight)
Desvio Padrão = 40.08097

sum(abs(cdc$weight - mean(cdc$weight)) <= sd(cdc$weight)) / nrow(cdc) 
Aproximadamente 71%

### 7

Assuntos abordados: Desvio padrão, média, mediana, as informações do sumário, tipos de dados.
Assuntos não abordados: Plotagem de gráficos.
Já vi esses conceitos em um curso introdutório ao promovido no LCCV em 2015, pelo aluno Leonildo Melo. 
