---
layout: post
title: Visualize Correlation Matrix with Cluster Analysis
author: <a href="http://taiyun.github.com/">Taiyun</a>
---





We can do hierarchical cluster analysis and reorder the correlation matrix based on the clusters; 
then visualize it and draw clusters squares on the graph. 



{% highlight r %}
library(corrplot)
M <- cor(mtcars)
corrplot(M, order = "hclust", addrect = 2, tl.pos = "d")
{% endhighlight %}

<img src="http://i.imgur.com/ltTAf.png" width="600px" height="600px" style="display:block; margin: auto" alt="plot of chunk corrplot-CM" title="plot of chunk corrplot-CM" /> 


