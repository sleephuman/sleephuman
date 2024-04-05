```R
( W <- sqrt( 2*qf(0.9, 2, 23) ) )
b0 <- lm.Toluca$coefficients[1] 
b1 <- lm.Toluca$coefficients[2] 
X.mean <- mean(로트크기)
MSE <- lm.Toluca.summary$sigma^2
n <- 25
SSX <- sum((로트크기-X.mean)^2)
X <- 100
b0+b1*X
b0+b1*X - W*sqrt(MSE)*sqrt(1/n + (X-X.mean)^2/SSX);
b0+b1*X + W*sqrt(MSE)*sqrt(1/n + (X-X.mean)^2/SSX)

X <- seq(20, 120, 0.5)
lower.bound <- b0+b1*X - W*sqrt(MSE)*sqrt(1/n + (X-X.mean)^2/SSX)
upper.bound <- b0+b1*X + W*sqrt(MSE)*sqrt(1/n + (X-X.mean)^2/SSX)
## 그림 2.6
plot(작업시간~로트크기, xlab="로트크기 X", ylab="시간 Y", 
     main="그림 2.6 회귀선의 신뢰띠")
abline(lm.Toluca)
lines(X,lower.bound, type="l", lwd=2)
lines(X,upper.bound, type="l", lwd=2)
```
