# Lab 4 B: Foundations for Statistical Inference

## Sua Vez
### 1

n_samps = 50

samp_size = 60

samp_mean <- rep(NA, n_samps)

samp_sd <- rep(NA, n_samps)

for (i in 1:n_samps) {

samp <- sample(area, samp_size)

samp_mean[i] <- mean(samp)

samp_sd[i] <- sd(samp)

}

samp_lower <- samp_mean - 1.96 * samp_sd / sqrt(samp_size

)samp_upper <- samp_mean + 1.96 * samp_sd / sqrt(samp_size)

plot_ci(samp_lower, samp_upper, mean(area))

Cerca de 48/50 (96%) incluem a média populacional real, a proporção não é exatamente igual a 95% devido à variação por causa da aleatoriedade nas amostras.

### 2

90% = 1.645.

### 3

samp_lower <- samp_mean - 1.645 * samp_sd / sqrt(samp_size)

samp_upper <- samp_mean + 1.645 * samp_sd / sqrt(samp_size)

plot_ci(samp_lower, samp_upper, mean(area))

Os intervalos de confiança 46/50 (92%) possuem a média populacional, 46/50 é bastante semelhante ao que é esperado, 45/50.

### 4

Intervalos de confiança, nivel de confiança e outros.
