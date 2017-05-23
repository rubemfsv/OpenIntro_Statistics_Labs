# Lab 5: Inference for Numerical Data

## Sua Vez
### 1

inference(y = nc$weeks, est = "mean", type = "ci", alternative = "twosided", method = “theoretical")

O intervalo de confiança de 95% para a duração média de gravidez, weeks, se encontra entre 38.15 e 38.52.

### 2

inference(y = nc$weeks, est = "mean", type = "ci", alternative = "twosided", method = "theoretical", conflevel=0.90)

O intervalo de confiança de 90% para a duração média de gravidez, weeks, se encontra entre 38.18 e 38.49.

### 3

levels(nc$mature)

qplot(data=nc, sample=gained, color=mature)

by(nc$gained, nc$mature, length)

inference(y=nc$gained, x=nc$mature, est="mean", type="ht", null=0, alternative=“twosided", method="theoretical", conflevel=0.95, order=c("younger mom", "mature mom”))

H0 é a diferença no peso médio ganho entre o grupo de mães mais jovens e o grupo de mãe mais velhas é 0, enquanto HA explana a diferença no peso ganho médio entre o grupo de mães mais jovens e os de mãe mais velhas é diferente de 0. Para nosso teste de dois lados, foi obtido um valor p de 0.1686, não é menos que 0.05, então, não temos evidências suficientes para rejeitar a hipótese nula; e não há evidências suficientes para apoiar a hipótese de que mães mais velhas e as mais jovens tem um aumento de peso diferente durante o processo de gravidez.

### 4

by(nc$mage, nc$mature, summary)

nc$mature: mature mom

Min. 1st Qu. Median Mean 3rd Qu. Max. = 
35.00 35.00 37.00 37.18 38.00 50.00

nc$mature: younger mom

Min. 1st Qu. Median Mean 3rd Qu. Max. = 
13.00 21.00 25.00 25.44 30.00 34.00

Aparentemente, temos que 35 é o limite de idade para as mães mais jovens e mais velhas, já que a mais velha e mais jovem possui 34 anos, e a mais velha mais jovem tem 35 anos.

### 5

A diferença de idade de mães são diferentes para mães brancas e mães não brancas? E relacionado a mães mais velhas e mais jovens?

d <- na.omit(data.frame(mofa_diff=nc$mage - nc$fage, whitemom=nc$whitemom, mature=nc$mature))

qplot(data=d, sample=mofa_diff, color=whitemom)

qplot(data=d, sample=mofa_diff, color=mature)

H0: A diferença das condições é 0;

HA: A diferença é diferente de 0.

inference(y=d$mofa_diff, x=d$whitemom, est="mean", type="ht", null=0, alternative=“twosided", method="theoretical", conflevel=0.95, order=c("white", "not white"))

inference(y=d$mofa_diff, x=d$mature, est="mean", type="ht", null=0,

alternative=“twosided", method="theoretical", conflevel=0.95, order=c("younger mom", "mature mom"))

### 6

Todos foram abordados em sala, e os desse capitulo foram difference of two means, inference e hypothesis test.
