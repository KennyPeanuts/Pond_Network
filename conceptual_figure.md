# Code to create figures for conceptual figure for the pond network grant

## Create Example Data

    #oc.burial.nopond <- sample(1:5, 200, replace = T)
    #oc.burial.pond <- c(sample(1:5, 150, replace = T), sample(50:70, 50, replace = T)) 
    oc.burial.nopond <- rnorm(20, 5, 5)
    oc.burial.pond <- c(rnorm(15, 5, 5), rnorm(5, 100, 5)) 
    burial <- c(oc.burial.nopond, oc.burial.pond)
    pond <- c(rep("no.pond", 20), rep("pond", 20))
    burial <- data.frame(pond, burial)
     
    boxplot(oc.burial.nopond, oc.burial.pond)
    text(1, mean(oc.burial.nopond), "*", cex = 3)
    text(2, mean(oc.burial.pond), "*", cex = 3)


    ggplot(burial, aes(x = pond, y = burial)) + geom_violin() + stat_summary(fun.data = "mean_sdl", mult = 1, geom = "pointrange")
   
    plot(density(oc.burial.pond), xlim = c(0, 100))
    plot(density(oc.burial.nopond), xlim = c(0, 100))
   
    plot(burial ~ as.numeric(pond), data = burial) 
    