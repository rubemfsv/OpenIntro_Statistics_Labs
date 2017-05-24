# Lab 3: Distributions

## Sua Vez
### 1

#### A) 

Gráfico B.

#### B) 

Gráfico C.

#### C) 

Gráfico D.

#### D) 

Gráfico A.

### 2

O pequeno padrão padrão passo passo é provavelmente devido ao arredondamento, pois, desvios maiores são dados não perfeitamente normais.

### 3

Primeiro, plotamos o gráfico da probabilidade normal para o diametro do joelho feminino:

qqnorm(females$kne.di, main='QQ - Diâmetro do Joelho Feminino')
qqline(females$kne.di)

O qqplot parece levemente desviado para a direita, pois tem vários valores na extremidade alta que são muito grandes. O qqplot também se parece com os dados tem um pouco grande demais de cauda esquerda para ser perfeitamente normal, mas o desvio não é muito.

Por último, fazemos um histograma 
hist(females$kne.di)

### 4

Abordados: Distribuição normal, distribuição geométrica, distribuição binomial.

Não abordados: Algumas distribuições discretas, porém, ficou como trabalho extra.

