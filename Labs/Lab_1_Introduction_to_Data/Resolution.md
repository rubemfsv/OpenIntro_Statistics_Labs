# Lab 1: Introduction to Data

## Exercício 1

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

## Exercício 2

Sumário para a altura: summary(cdc$height)
Sumário para a idade: summary(cdc$age)
Intervalo interquartílico para a altura: IQR(cdc$height)
Intervalo interquartílico para a idade: IQR(cdc$age)
Frequência relativa para gender: table(cdc$gender)/nrow(cdc)
Frequência relativa para exerany: table(cdc$exerany)/nrow(cdc)
Número de homens: sum(cdc$gender == 'm')
Proporção da amostra que se diz estar com saúde exelente: sum(cdc$genhlth == 'excellent')/nrow(cdc)

## Exercício 3

Primeiro, faremos o mosaico.

mosaicplot(table(cdc$gender, cdc$smoke100))

Notamos que a proporção de homens que fumaram mais de 100 cigarros  maior que a de mulheres.

## Exercício 4

under23_and_smoke <- subset(cdc, cdc$age < 23 & cdc$smoke100 == 1)

## Exercício 5

imc <- cdc$weight / cdc$height^2 * 703
boxplot(imc ~ cdc$genhlth)

O escolhido foi o exerany por causa da relação de se exercitar com o IMC. 
boxplot(imc ~ cdc$exerany)
Quando exerany é verdadeiro, nota-se que que o IMC  ligeiramente menor.
