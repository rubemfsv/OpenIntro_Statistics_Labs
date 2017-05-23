# Lab 6: Inference for Categorical Data

## Sua Vez
### 1
#### a
spain05 <- subset(atheism, nationality == "Spain" & year == "2005")

spain12 <- subset(atheism, nationality == "Spain" & year == "2012")

inference(spain05$response, est = "proportion", type = "ci", method = "theoretical", success = "atheist", conf = 0.95)

H0: Na Espanha não tem diferença entre a proporção de ateus em 2005 e 2012.

HA: Na Espanha tem uma diferença entre a proporção de ateus em 2005 e 2012.

Temos duas condições, a primeira é que as observações são independentes em cada amostra e entre as amostras, e, assumimos que seja sim. Após isso, tem a condição de sucesso / falha satisfeita para ambas as amostras tendo pelo menos 10 de cada sucesso e falha, porém, a função de inferência verifica isso, sua saída está abaixo, e sim, portanto, as condições são atendidas, sendo todos os grupos maiores que 10 observações. Os intervalos de confiança se sobrepõem, portanto não há evidência convincente para rejeitar a hipótese nula. A proporção de ateus na Espanha não teve uma mudança significativa em seus índices no nível de confiança de 95% entre os anos de 2005 e 2012.

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

