# retrospect_linear_regression

```

set.seed(10)
tt<-sort(rnorm(100))
knots<-seq(-2,2,length.out=6);knots<-knots[-c(1,length(knots))]
XX<-bs(tt,degree=2,knots=knots,intercept=TRUE)[,]
xx0<-bs(c(min(tt),1.5,max(tt)),degree=2,knots=knots,intercept=TRUE)[2,]

HH<-xx0%*%solve(t(XX)%*%XX)%*%t(XX)
plot(tt,c(HH))

```
