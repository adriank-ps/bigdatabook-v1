Installation instruction
---
##Requirements
* Java 8
* Python 3 with pip
* Scala
* ssh server
* pdsh
* Install required python components
    * `pip3 install py4j`
* We use Jupyter notebook, this step is optional
    * `pip3 install jupyter`
* Download and unpack [Apache Spark](https://spark.apache.org/downloads.html) in a directory where you want to place it.
    * We have used version 3.0.0-preview2, pre-built for Apache hadoop 3.2 and later
* Download and unpack [Apache Hadoop](https://hadoop.apache.org/releases.html) in a directory where you want to place it.
    * We have used version 3.2.1
* set environment variables, see prepare_env file for example
    * `SPARK_HOME=<path to Spark>`
    * `PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH`
    * `PYSPARK_PYTHON=<path to python>`
    * `PYSPARK_DRIVER_PYTHON="jupyter"`
    * `PYSPARK_DRIVER_PYTHON_OPTS="notebook"`
    * `JAVA_HOME=<path to jre>`
* For Apache Hadoop computer must be able to make ssh connection to localhost, we can check this with the fllowing command
    * `ssh localhost`
    * If it fails we need to execute these commands to create new ssh key and add it to list of autorised keys
        * ```bash
        ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
        cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
        chmod 0600 ~/.ssh/authorized_keys
        ```
