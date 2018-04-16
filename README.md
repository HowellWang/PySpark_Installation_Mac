PySpark installation guide for macOS
================================================================================
Tested with Apache Spark 2.1.0, Python 2.7.13 and Java 1.8.0_161

Install Java Development Kit
----------------------------
Download and install it from [oracle.com](https://java.com/en/download/)

Add following code to your  `.bash_profile` (Use "vim .bash_profile" to edit .bash_profile)
```bash
# For Apache Spark
if which java > /dev/null; then export JAVA_HOME=$(/usr/libexec/java_home); fi
```

Install Apache Spark
--------------------
You can use Mac OS package manager Brew ([http://brew.sh/](http://brew.sh/))
```shell
brew update (If you come across any issues, run "xcode-select --install" on terminal, then run "brew update" again)
brew install scala
brew install apache-spark
```

Set up env variables
--------------------
Add following code to your e.g. `.bash_profile`
```bash
# For a ipython notebook and pyspark integration
if which pyspark > /dev/null; then
  export SPARK_HOME="/usr/local/Cellar/apache-spark/2.1.0/libexec/"
  export PYTHONPATH=$SPARK_HOME/python:$SPARK_HOME/python/build:$PYTHONPATH
  export PYTHONPATH=$SPARK_HOME/python/lib/py4j-0.10.4-src.zip:$PYTHONPATH
fi
```

You can check `SPARK_HOME` path using following brew command
```shell
brew info apache-spark
```
You can start PySpark by following command

```shell
pyspark
```
