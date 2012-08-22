---
layout: post
title: Density Representation of the Scatterplot
author: <a href="http://taiyun.github.com/">Taiyun</a>
---





smoothScatter produces a smoothed color density representation of the scatterplot, obtained through a kernel density estimate. densCols produces a vector containing colors which encode the local densities at each point in a scatterplot.



{% highlight r %}
## A largish data set
n <- 10000
x1 <- matrix(rnorm(n), ncol = 2)
x2 <- matrix(rnorm(n, mean = 3, sd = 1.5), ncol = 2)
x <- rbind(x1, x2)
oldpar <- par(mfrow = c(2, 2))
smoothScatter(x, nrpoints = 0)
{% endhighlight %}



{% highlight text %}
## KernSmooth 2.23 loaded Copyright M. P. Wand 1997-2009
{% endhighlight %}



{% highlight r %}
smoothScatter(x)
## a different color scheme:
Lab.palette <- colorRampPalette(c("blue", "orange", "red"), space = "Lab")
smoothScatter(x, colramp = Lab.palette)
## somewhat similar, using identical smoothing computations, but
## considerably *less* efficient for really large data:
plot(x, col = densCols(x), pch = 20)
{% endhighlight %}

<img src="http://i.imgur.com/dc1si.png" width="600px" height="600px" style="display:block; margin: auto" alt="plot of chunk smoothScatter" title="plot of chunk smoothScatter" /> 


