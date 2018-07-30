# Joint Statistical Meeting 2018

## Distributed Machine Learning with H2O

### Prerequisites for H2O

[H2O-3 Requirements](http://h2o-release.s3.amazonaws.com/h2o/rel-wolpert/9/docs-website/h2o-docs/welcome.html#requirements)

### Install H2O in R
```
# The following two commands remove any previously installed H2O packages for R.
if ("package:h2o" %in% search()) { detach("package:h2o", unload=TRUE) }
if ("h2o" %in% rownames(installed.packages())) { remove.packages("h2o") }

# Next, we download packages that H2O depends on.
pkgs <- c("RCurl","jsonlite")
for (pkg in pkgs) {
if (! (pkg %in% rownames(installed.packages()))) { install.packages(pkg) }
}

# Now we download, install and initialize the H2O package for R.
install.packages("h2o", type="source", repos="http://h2o-release.s3.amazonaws.com/h2o/rel-wright/3/R")

# Finally, let's load H2O and start up an H2O cluster
library(h2o)
h2o.init()
```

### Running R script

* The [R](https://github.com/navdeep-G/jsm-2018/blob/master/h2o_airlines.R) script is meant to be run in a multi-node (EC2 or cluster of CPU's) setup as the data used is quite large (airlines dataset)
* [Here](https://github.com/navdeep-G/h2o-ec2) is a guide to setup your own EC2 instance with the latest H2O-3