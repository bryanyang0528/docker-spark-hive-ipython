# docker-spark-hive-ipython
# Introduction

感謝各位參加Hadoop Conference 2015
為了方便各位實作，將協助各位使用docker在本機上建立spark教學環境．
較熟悉Docker的朋友可以直接跳過這段．

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

# Enter the Jupyter

- linux: Type the web address `http://localhost:8888` in any browser. The link of Spark UI is `http://localhost:4040`.
- Mac:(for boot2docker) In your terminal, press `boot2docker ip` confirm the ip address of boot2docker，the type `http://<boot2docker ip>:8888`in the browser.

#### SparkContext(as **sc**) and SqlContext(as **sqlContext**) will generate automatically when you open a new notebook. 
