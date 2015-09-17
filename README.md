# docker-spark-hive-ipython
# Introduction

- Apache Hive (trunk version)
- Apache Tez 0.5.2
- Apache Hadoop 2.5.2
- PostgreSQL 9.3 (Hive metastore backend)
- Apach Spark 1.4.1
- Jupyter

# Install Docker

- Linux：https://docs.docker.com/linux/step_one/
- Mac：https://docs.docker.com/installation/mac/
  - Install boot2docker
  - **Recommand** Simulate a pure Linux(like Ubuntu) enviroment in VMWARE and install docker in it.

# **Attention** for boot2docker user
The default memory of boot2docker is only 2G, and recommended system requirement is 4G. 
There may be some unexpection problem if memory is not enough. 
You can change the default memory setting in following way:
 
- `vim ~/.boot2docker/profile`
- add `Memory = 4096` in this file.
* **Attention** The following process will reset your boot2docker, it's mean your images and caontainers will be erased.
- boot2docker stop
- boot2docker destroy
- boot2docker init
- boot2docker start

# Recommended System Requirement 
- CPU 4core
- RAM 4G up
- HDD 10G up (4G for Docker images)

# Pull The Docker Image

- `docker pull bryanyang0528/docker-spark-hive-ipython`

# Build The Docker Image

- Install git first
- Enter a apropriate directory
- `git clone https://github.com/bryanyang0528/docker-spark-hive-ipython.git`
- `cd docker-spark-hive-ipython`
- `docker build .`  
- `docker images`   confirm the images id
- `docker tag <images id> docker-spark-hive-ipython:latest`

# Run the Docker Image

- `docker run -d -p 8888:8888 -p 4040:4040 --name pyspark bryanyang0528/docker-spark-hive-ipython`

# Launch the Jupyter

- linux: Type the web address `http://localhost:8888` in any browser. The link of Spark UI is `http://localhost:4040`.
- Mac:(for boot2docker) In your terminal, press `boot2docker ip` confirm the ip address of boot2docker，the type `http://<boot2docker ip>:8888`in the browser.

#### SparkContext(as **sc**) and SqlContext(as **sqlContext**) will launch automatically when you open a notebook. 
