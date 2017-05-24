# Exercise - Chapter 3, Section 3.5

### 3.40

A principio, definiremos que a probabilidade de obter um sucesso (P(sucesso)) = 0.65 e a probabilidade de não obter o sucesso (P(não sucesso)) = 1 - 0.65 = 0.35.

#### A) A probabilidade de atingir o centro do círculo pela décima vez na décima quinta tentativa.

É sabido que essa distribuição é binomial negativa, portanto,

n-1 = 14, k - 1 = 9.

((14 * 13 * 12 * 11 * 10) / (5 * 4 * 3 * 2 * 1)) ((0.65) ^ 10) ((0.35) ^ 5) = 0.1415.

#### B) A probabilidade de atingir o centro dez vezes em quinze tentativas.

É sabido que essa distribuição é a binomial, portanto,

n = 15, k = 10.

((15 * 14 * 13 * 12 * 11 * 10) / (5 * 4 * 3 * 2 * 1)) ((0.65) ^ 10) ((0.35) ^ 5) = 0.2012.

#### C) A probabilidade de atingir a primeira vez o centro na terceira tentativa.

É sabido que essa distribuição é binomial negativa, portanto,

n - 1 = 2, k - 1 = 0.

((2 / 2) (0.65) ^ 1) ((0.35) ^ 2) = 0.0796.

### 3.42.

#### A) 

Utilizando a lógica da questão anterior, vamos usar a binomial negativa para calcular esta probabilidade. Portanto, temos P = (36 * 0.0033 * 0.3205) = 0.038, transformando em porcentagem, o resultado é 3,8%.

#### B) 

Devido a cada tentativa possuir a mesma probabilidade de acerto, então, a probabilidade de sucesso é igual a 15%.

#### C) 

Na alternativa A, consideramos para o cálculo da probabilidade todos os 3 acertos. Já na alternativa B, a tentativa em questão é a única que é levada em consideração.

### 3.44.

#### A) 

Distribuição de Poisson.

#### B) 

1 e 1.

#### C) 

Sim, pois 4 está a 3 desvios padrões da média.

#### D) 

A probabilidade de no máximo 2 erros chamaremos de P(A).

P(A) = P(0) + P(1) + P(2) = ((1^0)(e^-1) / 0!) + ((1^1)(e^-1) / 1!) + ((1^2)(e^-1) / 2!) = (1/e) + (1/e) + (1/2e) = 0.368 + 0.368 + 0.184 = 0.92.
