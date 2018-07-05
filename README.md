# learn-hadoop

## Step 1 - Download:
`docker pull angelcervera/docker-hadoop:2.7.1-single`

## Step 2 - Run:
`docker run --name my-new-hadoop-2.7.1 \
   -v /tmp/hadoop_image/logs:/opt/hadoop/logs \
   -v /tmp/hadoop_image/shared:/root/shared \
   -p 50070:50070 \
   -p 50075:50075 \
   -p 50060:50060 \
   -p 50030:50030 \
   -p 19888:19888 \
   -p 10033:10033 \
   -p 8032:8032 \
   -p 8030:8030 \
   -p 8088:8088 \
   -p 8033:8033 \
   -p 8042:8042 \
   -p 8188:8188 \
   -p 8047:8047 \
   -p 8788:8788 \
   -it angelcervera/docker-hadoop:2.7.1-single`

## Step 3 - Run example jar:
`/opt/hadoop/bin/hadoop jar /opt/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.1.jar pi 16 10000`

## Step 4 - Create Hello World:
In Process