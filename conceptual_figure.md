# Code to create figures for conceptual figure for the pond network grant

## Create Example Data
### Burial
    oc.burial.nopond <- rnorm(8, 1, 0.5)
    oc.burial.pond <- c(rnorm(6, 1, 0.5), rnorm(2, 10, 0.5)) 
    burial <- c(oc.burial.nopond, oc.burial.pond)
    pond <- c(rep("no.pond", 8), rep("pond", 8))
    burial <- data.frame(pond, burial)
     
    par(las = 1, mar = c(6, 6, 6, 6))
    boxplot(oc.burial.nopond, oc.burial.pond, ylim = c(0, 15), xlim = c(0.5, 2.5), ylab = "Relative Organic Carbon Storage", axes = F)
    axis(2)
    axis(1, c("Without Ponds", "With Ponds"), at = c(1, 2))
    text(1, mean(oc.burial.nopond), "*", cex = 3, col = 2)
    text(2, mean(oc.burial.pond), "*", cex = 3, col = 2)
    points(burial ~ jitter((as.numeric(pond) + 0.3), 0.3), data = burial, pch = 1, col = "dimgray")
    #box()

### Denitrification
    dn.nopond <- rnorm(8, 2, 5)
    dn.pond <- c(rnorm(6, 2, 5), rnorm(2, 200, 5)) 
    dn <- c(dn.nopond, dn.pond)
    pond <- c(rep("no.pond", 8), rep("pond", 8))
    dn <- data.frame(pond, dn)
     
    boxplot(dn.nopond, dn.pond, ylim = c(0, 250), width = c(1, 1))
    text(1, mean(dn.nopond), "*", cex = 3, col = 2)
    text(2, mean(dn.pond), "*", cex = 3, col = 2)
    points(dn ~ jitter((as.numeric(pond) + 0.5), 0.3), data = dn, col = "dark gray")

### N Storage
    Nstore.nopond <- rnorm(8, 10, 0.5)
    Nstore.pond <- c(rnorm(6, 10, 0.5), rnorm(2, 1, 0.5)) 
    Nstore <- c(Nstore.nopond, Nstore.pond)
    pond <- c(rep("no.pond", 8), rep("pond", 8))
    Nstore <- data.frame(pond, Nstore)
     
    par(las = 1, mar = c(6, 6, 6, 6))
    boxplot(Nstore.nopond, Nstore.pond, ylim = c(0, 15), xlim = c(0.5, 2.5), ylab = "Relative Nitrogen Storage", axes = F)
    axis(2)
    axis(1, c("Without Ponds", "With Ponds"), at = c(1, 2))
    text(1, mean(Nstore.nopond), "*", cex = 3, col = 2)
    text(2, mean(Nstore.pond), "*", cex = 3, col = 2)
    points(Nstore ~ jitter((as.numeric(pond) + 0.3), 0.3), data = Nstore, pch = 1, col = "dimgray")
    #box()
    
### Beta Diversity
    B.nopond <- rnorm(8, 1, 0.1)
    B.pond <- c(rnorm(4, 1, 0.1), rnorm(4, 2, 0.1)) 
    B <- c(B.nopond, B.pond)
    pond <- c(rep("no.pond", 8), rep("pond", 8))
    B <- data.frame(pond, B)
     
    par(las = 1, mar = c(6, 6, 6, 6))
    boxplot(B.nopond, B.pond, ylim = c(0, 3), xlim = c(0.5, 2.5), ylab = "Relative Beta Diversity", axes = F)
    axis(2)
    axis(1, c("Without Ponds", "With Ponds"), at = c(1, 2))
    text(1, mean(B.nopond), "*", cex = 3, col = 2)
    text(2, mean(B.pond), "*", cex = 3, col = 2)
    points(B ~ jitter((as.numeric(pond) + 0.3), 0.3), data = B, pch = 1, col = "dimgray")
    #box()