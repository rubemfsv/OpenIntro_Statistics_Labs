# Lab 7: Intro to Linear Regression

## Sua Vez
### 1

Variável escolhida: Hits

plot(runs ~ hits, data=mlb11)

m2 <- lm(runs ~ hits, data = mlb11)

abline(m2)

cor(mlb11$runs, mlb11$hits)

### 2

Sim, parece.

A justificativa é simples, pois hits R^2 (= 0.64) com runs (R = 0.80) é maior do que at_bats R^2 (= 0.37) com runs (R = 0.61), então, nota-se que hits é um melhor preditor para corridas do que at_bats.

### 3

Percebemos que runs vs bat_avg tem o maior R^2 (= 0,66) e também aparenta atender aos critérios de regressão linear, que são resíduos normais, variância constante, linear.

preds = c('at_bats', 'hits', 'homeruns', 'bat_avg', 'strikeouts', 'stolen_bases', 'wins')

for (p in preds) {

R = cor(mlb11[, p], mlb11$runs)

print(paste(p, ': ', R ^ 2, sep=''))

}

plot(runs ~ bat_avg, data=mlb11)

m3 <- lm(runs ~ bat_avg, data=mlb11)

abline(m3)

### 4

Agora, podemos ver que as novas variáveis são muito mais eficazes na previsão de runs do que nas antigas.

O preditor com o melhor R^2 (= 0,93), new_obs, tem uma relação linear com runs e atende aos dois critérios residuais.

preds = c('new_onbase', 'new_slug', 'new_obs')

for (p in preds) {

R = cor(mlb11[, p], mlb11$runs)

print(paste(p, ': ', R ^ 2, sep=''))

}

plot(runs ~ new_obs, data=mlb11)

m4 <- lm(runs ~ new_obs, data=mlb11)

abline(m4)

### 5

Por fim, como foi citado na última pergunta, o diagrama de dispersão parece satisfazer os três critérios de regressão linear. O histograma de resíduos e qq-plot parecem mostrar mais normalidade do que at_bats.

hist(m4$residuals)

qqnorm(m4$residuals)

qqline(m4$residuals)

### 6

Resíduos e correlação, colocação de uma reta por regressão de mínimos quadrados, tipos de valores abertos em regressão linear e inferência para regressão linear.
