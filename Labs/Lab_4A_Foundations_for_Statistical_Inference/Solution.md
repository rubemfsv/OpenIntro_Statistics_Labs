# Lab 4 A: Foundations for Statistical Inference

## Sua Vez
### 1

samp <- sample(price, 50)
mean(samp)

O resultado seria 190760.8.

### 2

sample_means_50 <- rep(NA, 5000)
for (i in 1:5000) {
sample_means_50[i] <- mean(sample(price, 50))
}

hist(sample_means_50)

mean(sample_means_50) #180977.5

sd(sample_means_50) #11147.26

mean(price) #180796.1

Os outputs estão comentadas depois da cerquilha.

### 3

sample_means_150 <- rep(NA, 5000)
for (i in 1:5000) {
sample_means_150[i] <- mean(sample(price, 150))
}

hist(sample_means_150, breaks=25)

mean(sample_means_150) #180701.7

sd(sample_means_150) #6279.891

A distribuição de amostragem da média de 150 amostras da população de preços é aproximadamente normal, com uma média de cerca de $180.000 e um desvio padrão de cerca de $6.300.

### 4

A distribuição de amostragem da média de 150 amostras tem uma dispersão menor. Se quiséssemos aproximar o parâmetro da população com a maior precisão possível, iriamos querer uma dispersão menor e, portanto, um tamanho de amostra maior.

### 5

Variabilidade de estimativas, distribuição amostras desconhecida, tamanho da amostra e distribuição amostral.
