library(parallel)
no_cores <- detectCores() - 1
cl <- makeCluster(no_cores)
ex.df <- data.frame(a=rnorm(1000000), b = rnorm(1000000), c = rnorm(1000000))

parCapply(cl, ex.df, mean)
apply(ex.df, 2, mean)
stopCluster(cl)
