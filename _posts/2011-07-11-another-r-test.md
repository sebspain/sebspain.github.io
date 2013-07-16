---
layout: post
comments: false
title: another R test
---

To plot the following graph

```{r}
fret_raw<-read.table("FRET_kinetics.txt", header=T)
attach(fret_raw)
plot(Time_min, baseline_diln, ylim=c(-10,110), xlab="", ylab="", type="l", lwd=2, lty=2, xaxt="n", yaxt="n")
par(new=T)
plot(Time_min, baseline_C, ylim=c(-10,110), xlab="", ylab="", col="blue", xaxt="n", yaxt="n", type="l", lwd=2, lty=2)
par(new=T)
plot(Time_min, baseline_D, ylim=c(-10,110), xlab="", ylab="", col="red", xaxt="n", yaxt="n", type="l", lwd=2, lty=2)
help(axis)
axis(1, at=c(0,10,20,30,40), )
axis(2, at=c(0,20,40,60,80,100) )
mtext("Fluoresence / AU", 2, line=2.5, cex=1.5)
mtext("Time / min", 1, line=2.5, cex=1.5)
```

```{r}
sessionInfo()
```

output:

```
## R version 2.15.1 (2012-06-22)
## Platform: x86_64-pc-linux-gnu (64-bit)
## 
## locale:
##  [1] LC_CTYPE=en_GB.UTF-8       LC_NUMERIC=C              
##  [3] LC_TIME=en_GB.UTF-8        LC_COLLATE=en_GB.UTF-8    
##  [5] LC_MONETARY=en_GB.UTF-8    LC_MESSAGES=en_GB.UTF-8   
##  [7] LC_PAPER=C                 LC_NAME=C                 
##  [9] LC_ADDRESS=C               LC_TELEPHONE=C            
## [11] LC_MEASUREMENT=en_GB.UTF-8 LC_IDENTIFICATION=C       
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## other attached packages:
## [1] knitr_1.2
## 
## loaded via a namespace (and not attached):
## [1] digest_0.6.3   evaluate_0.4.4 formatR_0.8    stringr_0.6.2 
## [5] tools_2.15.1
```
