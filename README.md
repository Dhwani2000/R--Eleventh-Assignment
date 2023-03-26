# R--Eleventh-Assignment

> tukey_multiple <- function(z) {
+   outliers <- array(TRUE,dim=dim(z))
+   for (j in 1:ncol(z))
+   {
+    outliers[,j] <- outliers[,j] && tukey.outlier(z[,j])
+   }
+   outliers.vec <-vector(length=nrow(z))
+   for (i in 1:nrow(z))
+   {
+    outliers.vec[i] <- all(outliers[i,])
+   }
+   return(outliers.vec)
+   }

> traceback()
No traceback available 

> debug(tukey_multiple)
> tukey_multiple(z)

debugging in: tukey_multiple(z)
debug at #1: {
    outliers <- array(TRUE, dim = dim(z))
    for (j in 1:ncol(z)) {
        outliers[, j] <- outliers[, j] && tukey.outlier(z[, j])
    }
    outliers.vec <- vector(length = nrow(z))
    for (i in 1:nrow(z)) {
        outliers.vec[i] <- all(outliers[i, ])
    }
    return(outliers.vec)
}
Browse[2]> n
debug at #2: outliers <- array(TRUE, dim = dim(z))
Browse[2]> n
Error in array(TRUE, dim = dim(z)) : object 'z' not found


> z <- matrix(rnorm(100), ncol=5)


> tukey_multiple(z)
debugging in: tukey_multiple(z)
debug at #1: {
    outliers <- array(TRUE, dim = dim(z))
    for (j in 1:ncol(z)) {
        outliers[, j] <- outliers[, j] && tukey.outlier(z[, j])
    }
    outliers.vec <- vector(length = nrow(z))
    for (i in 1:nrow(z)) {
        outliers.vec[i] <- all(outliers[i, ])
    }
    return(outliers.vec)
}
Browse[2]> n
debug at #2: outliers <- array(TRUE, dim = dim(z))
Browse[2]> n
debug at #3: for (j in 1:ncol(z)) {
    outliers[, j] <- outliers[, j] && tukey.outlier(z[, j])
}
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] && tukey.outlier(z[, j])
Browse[2]> n

Error in tukey.outlier(z[, j]) : could not find function "tukey.outlier"
In addition: Warning message:
In outliers[, j] && tukey.outlier(z[, j]) :
  'length(x) = 20 > 1' in coercion to 'logical(1)'
  
  
>  tukey_multiple <- function(z) {
+   outliers <- array(TRUE,dim=dim(z))
+   for (j in 1:ncol(z))
+   {
+    outliers[,j] <- outliers[,j] & tukey.outlier[,j]
+   }
+   outliers.vec <-vector(length=nrow(z))
+   for (i in 1:nrow(z))
+   {
+    outliers.vec[i] <- all(outliers[i,])
+   }
+   return(outliers.vec)
+   }

> debug(tukey_multiple)
> 
> tukey_multiple(z)

debugging in: tukey_multiple(z)
debug at #1: {
    outliers <- array(TRUE, dim = dim(z))
    for (j in 1:ncol(z)) {
        outliers[, j] <- outliers[, j] & tukey.outlier[, j]
    }
    outliers.vec <- vector(length = nrow(z))
    for (i in 1:nrow(z)) {
        outliers.vec[i] <- all(outliers[i, ])
    }
    return(outliers.vec)
}

Browse[2]> n
debug at #2: outliers <- array(TRUE, dim = dim(z))
Browse[2]> n
debug at #3: for (j in 1:ncol(z)) {
    outliers[, j] <- outliers[, j] & tukey.outlier[, j]
}
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #5: outliers[, j] <- outliers[, j] & tukey.outlier[, j]
Browse[2]> n
debug at #7: outliers.vec <- vector(length = nrow(z))
Browse[2]> n
debug at #8: for (i in 1:nrow(z)) {
    outliers.vec[i] <- all(outliers[i, ])
}
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> n
debug at #10: outliers.vec[i] <- all(outliers[i, ])
Browse[2]> Q
