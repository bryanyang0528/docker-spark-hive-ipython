# docker-spark-hive-ipython
# 前言

感謝各位參加Hadoop Conference 2015
為了方便各位實作，將協助各位使用docker在本機上建立spark教學環境．
較熟悉Docker的朋友可以直接跳過這段．

# Docker安裝教學

- Linux環境餐請參考：https://docs.docker.com/linux/step_one/
- Mac環境請參考：https://docs.docker.com/installation/mac/
  - 可以安裝boot2docker
  - **推薦先用VMWARE建立純linux環境後再安裝docker**

# 使用boot2docker特別注意
因為預設的記憶體只有2G，本包可能需要至少**4G**的記憶體，若執行時遇到記憶體不足的問題，請按照下列步驟修改．
- `vim ~/.boot2docker/profile`
- 在檔案中加入 Memory = 4096
*!!以下步驟將會重置您的boot2docker，亦即所有的images都會刪除，請謹慎使用!!*
- boot2docker stop
- boot2docker destroy
- boot2docker init
- boot2docker start

# 系統需求
- CPU 4core
- RAM 4G以上
- HDD 10G以上(Docker images檔約4G)

# 方法一：直接拉取Docker Images

- `docker pull bryanyang0528/docker-spark-hive-ipython`
(拉取成功後就不用再自行Build Images，直接跳執行)

# 方法二：建立Docker Images

- 請確認您的電腦上已經安裝git
- 進入任意合適的目錄
- `git clone https://github.com/bryanyang0528/docker-spark-hive-ipython.git`
- `cd docker-spark-hive-ipython`
- `docker build .`  此步驟將會開始建立docker images
- `docker images`   確認新建立的images id (一個英數組合)
- `docker tag <images id> docker-spark-hive-ipython:latest`

# 執行Docker Images

- `docker run -d -p 8888:8888 -p 4040:4040 --name pyspark bryanyang0528/docker-spark-hive-ipython`

# 進入ipython

- linux: 直接在瀏覽器輸入`http://localhost:8888` , Spark的UI在`http://localhost:4040`
- Mac: 請先在terminal中輸入 `boot2docker ip` 確認ip位置，再到瀏覽器中輸入`http://<boot2docker ip>:8888`


