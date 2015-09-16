# docker-spark-hive-ipython
# 前言

感謝各位參加Hadoop Conference 2015
為了方便各位實作，將協助各位使用docker在本機上建立spark教學環境．
較熟悉Docker的朋友可以直接跳過這段．

# Docker安裝教學

- Linux環境餐請參考：(https://docs.docker.com/linux/step_one/)
- Mac環境請參考：(https://docs.docker.com/installation/mac/)

# 建立Docker Images

- 請確認您的電腦上已經安裝git
- 進入任意合適的目錄
- `git clone https://github.com/bryanyang0528/docker-spark-hive-ipython.git`
- `cd docker-spark-hive-ipython`
- `docker build .`  此步驟將會開始建立docker images
- `docker images`   確認新建立的images id (一個英數組合)
- `docker tag <images id> pyspark:1.4.1`
- `docker run -d -p 8888:8888 -p 4040:4040 --name pyspark pyspark:1.4.1`

# 進入ipython

- linux: 直接在瀏覽器輸入`http://localhost:8888` , Spark的UI在`http://localhost:4040`
- Mac: 請先在terminal中輸入 `boot2docker ip` 確認ip位置，再到瀏覽器中輸入`http://<boot2docker ip>:8888`

