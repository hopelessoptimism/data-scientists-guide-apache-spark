# The Data Scientist's Guide to Apache Spark

[![Discord badge](https://img.shields.io/discord/830547562385113149?style=flat-square&color=%235865F2)](https://discord.gg/nbyZ6EpUum)
[![Twitter Follow badge](https://img.shields.io/badge/twitter-@jonathandinu-1da1f2?style=flat-square&logo=twitter)](https://twitter.com/jonathandinu)
[![YouTube Channel Subscribers](https://img.shields.io/badge/youtube-subscribe-FF0000?logo=youtube&style=flat-square)](https://www.youtube.com/channel/UCi0Hd3U6xb4V0ApUhAIfu9Q)

## Overview

This repo contains notebook exercises for a workshop teaching the best practices of using Spark for practicing data scientists in the context of a data scientist’s standard workflow. By leveraging Spark’s APIs for Python and R to present practical applications, the technology will be much more accessible by decreasing the barrier to entry.

## Materials

There are corresponding videos on Youtube walking through and presenting the materials in here.

> If you find any errors in the code or materials, please open a Github issue in this repository or send an email to inquiries@jonathan.industries

## Skill Level

Beginner to Intermediate

## Learn How To
* Use Python for distributed computing
* Scale data processing with Spark
* Conduct exploratory data analysis with PySpark
* Utilize parallel computing with Ray
* Scale machine learning and artificial intelligence applications with Ray

## Who Should Take This Course

This course is a good fit for anyone who needs to improve their fundamental understanding of scalable data processing with Python for use in machine learning or artificial intelligence applications.

## Prerequisites

* A basic understanding of programming in Python (variables, basic control flow, simple scripts).
* Familiarity with the vocabulary of data processing at scale, machine learning (dataset, training set, test set, model), and AI helpful but not required.

## Getting Started

To run locally in a docker container 👇

```
make jupyter
```

or 

```
docker run -p 8888:8888 -p 8265:8265 -p 8000:8000 -p 8089:8089 -v $(pwd):/home/jovyan/ --pull 'always' psychothan/scaling-data-science
```

Then open a web browser to the URL it spits out (the Jupyter server in the container uses [token authentication](https://jupyter-notebook.readthedocs.io/en/stable/security.html))

![notebook url](images/console.png)
![jupyter notebook](images/notebook.png)

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

## LICENSE

<p xmlns:cc="http://creativecommons.org/ns#" >This work by <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://jonathanjonathanjonathan.com">Jonathan Dinu</a> is licensed under <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">CC BY 4.0</a></p>

### You are free to:

* __Share__ — copy and redistribute the material in any medium or format
* __Adapt__ — remix, transform, and build upon the material
for any purpose, even commercially.

_The licensor cannot revoke these freedoms as long as you follow the license terms._

### Under the following terms:

* __Attribution__ — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
* __No additional restrictions__ — You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.

### Notices:

You do not have to comply with the license for elements of the material in the public domain or where your use is permitted by an applicable exception or limitation.

No warranties are given. The license may not give you all of the permissions necessary for your intended use. For example, other rights such as publicity, privacy, or moral rights may limit how you use the material.

