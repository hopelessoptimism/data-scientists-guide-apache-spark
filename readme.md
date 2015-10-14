# The Data Scientist's Guide to Apache Spark

[![Join the chat at https://gitter.im/Jay-Oh-eN/data-scientists-guide-apache-spark](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/Jay-Oh-eN/data-scientists-guide-apache-spark?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/zipfian/data-scientists-guide-apache-spark)

This repo contains notebook exercises for a workshop teaching the best practices of using Spark for practicing data scientists in the context of a data scientist’s standard workflow. By leveraging Spark’s APIs for Python and R to present practical applications, the technology will be much more accessible by decreasing the barrier to entry.

## Materials

For the workshop (and after) we will use a Gitter chatroom to keep the conversation going: https://gitter.im/Jay-Oh-eN/data-scientists-guide-apache-spark.

And/or please do not hesitate to reach out to me directly via email at jonathan@galvanize.com or over twitter @clearspandex

The presentation can be found on Slideshare [here](http://www.slideshare.net/jonathandinu/the-data-scientists-guide-to-apache-spark).


## Prerequisites

Prior experience with Python and the scientific Python stack is beneficial.  Also knowledge of data science models and applications is preferred.  This will not be an introduction to Machine Learning or Data Science, but rather a course for people proficient in these methods on a small scale to understand how to apply that knowledge in a distributed setting with Spark.

### Setup

* [Local Installation](http://www.slideshare.net/jonathandinu/the-data-scientists-guide-to-apache-spark/48)
* [Cluster Deployment](http://www.slideshare.net/jonathandinu/the-data-scientists-guide-to-apache-spark/69)

#### SparkR with a Notebook

1. Install [IRKernel](https://github.com/IRkernel/IRkernel)
  
```r
install.packages(c('rzmq','repr','IRkernel','IRdisplay'), repos = c('http://irkernel.github.io/', getOption('repos')))

IRkernel::installspec()
```

2. Set [environment variables](https://github.com/apache/spark/tree/master/R#using-sparkr-from-rstudio):

```
# Example: Set this to where Spark is installed
Sys.setenv(SPARK_HOME="/Users/[username]/spark")

# This line loads SparkR from the installed directory
.libPaths(c(file.path(Sys.getenv("SPARK_HOME"), "R", "lib"), .libPaths()))

# if these two lines work, you are all set
library(SparkR)
sc <- sparkR.init(master="local")
```

## Data

`link = 'http://hopelessoptimism.com/static/data/airline-data'`

The notebooks use a few datasets.  For the DonorsChoose data, you can read the documentation [here](http://data.donorschoose.org/) and download a zip (~0.5 gb) from: http://hopelessoptimism.com/static/data/donors_choose.zip

## IPython Console Help

Q: How can I find out all the methods that are available on DataFrame?

- In the IPython console type `sales.[TAB]`

- Autocomplete will show you all the methods that are available.

- To find more information about a specific method, say `.cov` type `help(sales.cov)`

- This will display the API documentation for that method.

## Spark Documentation

Q: How can I find out more about Spark's Python API, MLlib, GraphX,
Spark Streaming, deploying Spark to EC2?

- Go to <https://spark.apache.org/docs/latest>

- Navigate using tabs to the following areas in particular.

- Programming Guide > Quick Start, Spark Programming Guide,
  Spark Streaming, DataFrames and SQL, MLlib, GraphX, SparkR.

- Deploying > Overview, Submitting Applications, Spark Standalone,
  YARN, Amazon EC2.

- More > Configuration, Monitoring, Tuning Guide.

## References

### Setup

* [Spark on Windows 7](http://nishutayaltech.blogspot.in/2015/04/how-to-run-apache-spark-on-windows7-in.html)

### History of Computing

* [Why CPUs aren't getting any faster](http://www.technologyreview.com/view/421186/why-cpus-arent-getting-any-faster/)
* [Hadoop: A brief History](research.yahoo.com/files/cutting.pdf)
* [The State of Spark: And where we are going next](https://spark-summit.org/2013/wp-content/uploads/2013/10/Zaharia-spark-summit-2013-matei.pdf)
* https://blogs.apache.org/foundation/entry/the_apache_software_foundation_announces50

### Original Papers

* [Matei's Thesis](http://www.eecs.berkeley.edu/Pubs/TechRpts/2014/EECS-2014-12.pdf)
* [Original (RDD) Paper](https://www.cs.berkeley.edu/~matei/papers/2012/nsdi_spark.pdf)

### Data Science with Spark

* http://blog.cloudera.com/blog/2015/07/how-to-do-data-quality-checks-using-apache-spark-dataframes/

### Distributed Computing

* [Distributed Systems for Fun and Profit](http://book.mixu.net/distsys/intro.html)
* [Resilience Engineering: Learning to Embrace Failure](http://queue.acm.org/detail.cfm?id=2371297)
* [Chaos Monkey](https://github.com/Netflix/SimianArmy/wiki/Chaos-Monkey)

### Spark Internals

* [PySpark Internals](https://cwiki.apache.org/confluence/display/SPARK/PySpark+Internals)
* [A deeper understanding of Spark's internals](https://spark-summit.org/2014/wp-content/uploads/2014/07/A-Deeper-Understanding-of-Spark-Internals-Aaron-Davidson.pdf)

### Spark Performance

* [Tuning and Debugging in Apache Spark](http://www.slideshare.net/pwendell/tuning-and-debugging-in-apache-spark)
* [`reduceByKey` vs `groupByKey`](https://github.com/databricks/spark-knowledgebase/blob/master/best_practices/prefer_reducebykey_over_groupbykey.md)
* [Advanced Spark](https://databricks-training.s3.amazonaws.com/slides/advanced-spark-training.pdf)
* [What's the difference between `cache()` and `persist()`](http://stackoverflow.com/questions/26870537/spark-what-is-the-difference-between-cache-and-persist)
* [Monitoring and Instrumentation](http://spark.apache.org/docs/latest/monitoring.html)

### Spark Deployment

* [A Tale of two clusters: Mesos vs. YARN](http://radar.oreilly.com/2015/02/a-tale-of-two-clusters-mesos-and-yarn.html)

### Plotly + Spark

* https://plot.ly/ipython-notebooks/apache-spark/
* https://plot.ly/python/ipython-notebooks/
* https://plot.ly/python/matplotlib-to-plotly-tutorial/#6.1-Matplotlib-to-Plotly-conversion-basics

### word2Vec

> The word2vec tool takes a text corpus as input and produces the word vectors as output. It first constructs a vocabulary from the training text data and then learns vector representation of words. The resulting word vector file can be used as features in many natural language processing and machine learning applications.

#### Theory/Application

* [Efficient Estimation of Word Representations in
Vector Space](http://arxiv.org/pdf/1301.3781.pdf)
* [Distributed Representations of Words and Phrases
and their Compositionality](http://papers.nips.cc/paper/5021-distributed-representations-of-words-and-phrases-and-their-compositionality.pdf)
* [Distributed Representations of Sentences and Documents](http://arxiv.org/pdf/1405.4053v2.pdf)
* [deeplearning4j tutorial (with applications)](http://deeplearning4j.org/word2vec.html)
* [Modern Methods for Sentiment Analysis](https://districtdatalabs.silvrback.com/modern-methods-for-sentiment-analysis)
* [word2vec: an introduction](http://www.folgertkarsdorp.nl/word2vec-an-introduction/)

#### Tools

* [Spark MLlib (Python, Scala)](http://spark.apache.org/docs/latest/mllib-feature-extraction.html#word2vec)
* [deeplearning4j (Java)](http://deeplearning4j.org/word2vec.html)
* [gensim: word2vec and doc2vec (Python)](https://radimrehurek.com/gensim/models/word2vec.html)

Books on Spark
--------------

- Learning Spark: Lightning-Fast Big Data Analytics    
  By Holden Karau, Andy Konwinski, Patrick Wendell, Matei Zaharia    
  Publisher: O'Reilly Media, June 2014    
  <http://shop.oreilly.com/product/0636920028512.do>    
  Introduction to Spark APIs and underlying concepts.

- Spark Knowledge Base    
  By Databricks, Vida Ha, Pat McDonough    
  Publisher: Databricks    
  <http://databricks.gitbooks.io/databricks-spark-knowledge-base>    
  Spark tips, tricks, and recipes.    

- Spark Reference Applications    
  By Databricks, Vida Ha, Pat McDonough    
  Publisher: Databricks    
  <http://databricks.gitbooks.io/databricks-spark-reference-applications>    
  Best practices for large-scale Spark application architecture.
  Topics include import, export, machine learning, streaming.

Learning Scala
--------------

- Scala for the Impatient    
  by Cay S. Horstmann    
  Publisher: Addison-Wesley Professional, March 2012    
  <http://www.amazon.com/Scala-Impatient-Cay-S-Horstmann/dp/0321774094>    
  Concise, to the point, and contains good practical tips on using Scala. 

Video Tutorials
---------------

- Spark Internals    
  By Matei Zaharia (Databricks)    
  <https://www.youtube.com/watch?v=49Hr5xZyTEA>    

- Spark on YARN    
  By Sandy Ryza (Cloudera)    
  <https://www.youtube.com/watch?v=N6pJhxCPe-Y>    

- Spark Programming    
  By Pat McDonough (Databricks)    
  <https://www.youtube.com/watch?v=mHF3UPqLOL8>    

Community
---------

- Community    
  <https://spark.apache.org/community.html>    
  Spark's community page lists meetups, mailing-lists, and upcoming
  Spark conferences.

- Meetups    
  <http://spark.meetup.com/>    
  Spark has meetups in the Bay Area, NYC, Seattle, and most major
  cities around the world.

- Mailing Lists    
  <https://spark.apache.org/community.html>    
  The user mailing list covers issues and best practices around using
  Spark. The dev mailing list is for people who want to contribute to
  Spark.


