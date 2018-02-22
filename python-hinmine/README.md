[![CHUV](https://img.shields.io/badge/CHUV-LREN-AF4C64.svg)](https://www.unil.ch/lren/en/home.html) [![DockerHub](https://img.shields.io/badge/docker-hbpmip%2Fjava--rapidminer--naivebayes-008bb8.svg)](https://hub.docker.com/r/hbpmip/java-rapidminer-naivebayes/) [![ImageVersion](https://images.microbadger.com/badges/version/hbpmip/java-rapidminer-knn.svg)](https://hub.docker.com/r/hbpmip/java-rapidminer-knn/tags "hbpmip/java-rapidminer-knn image tags") [![](https://images.microbadger.com/badges/version/hbpmip/java-rapidminer-naivebayes.svg)](https://microbadger.com/images/hbpmip/java-rapidminer-naivebayes "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/hbpmip/java-rapidminer-naivebayes.svg)](https://microbadger.com/images/hbpmip/java-rapidminer-naivebayes "Get your own image badge on microbadger.com")

# Python HINMine

HINMine algorithm for network-based propositionalization

## Algorithm description

The HINMINE algorithm for network-based propositionalization is an algorithm for data analysis based on network analysis methods.

The input for the algorithm is a data set containing instances with real-valued features. The purpose of the algorithm is to construct a new set of features for further analysis by other data mining algorithms. The algorithm outputs a data set with features, generated for each data instance in the input data set. The features represent how close a given instance is to the other instances in the data set. The closeness of instances is measured using the PageRank algorithm, calculated on a network constructed from instance similarities.

The algorithm has two parameters:

  - normalize: [default value True] This parameter is a boolean parameter which tells the algorithm whether it should first normalize the data. Data normalization normalizes the range of each feature to [-1, 1] and can be useful when comparing two instances. However, if two features have different values for a non-arbitrary reason, normalization should not be performed
  - damping: [default value 0.85] This parameter is the damping factor of the PageRank algorithm used in calculating feature values for the data instances. It represents the probability of a random walker in a network to continue its random walk as oposed to teleporting to a random node



## Build (for contributors)

Run: `./build.sh`


## Test (for contributors)

Run: `./tests/test.sh`


## Publish (for contributors)

Run: `./publish.sh`
