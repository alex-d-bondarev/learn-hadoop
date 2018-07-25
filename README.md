# learn-hadoop

## Step 1 - Set up IDE jar:
Project Structure > Artifacts > Add Jar > From modules with dependencies
**Note:** Do not forget to add main class

## Step 2 - Build Artifact:
- Open Main class
- Build > Build Artifacts

## Step 3 - Start docker:
**Note:** Change `/Users/oleksandrbondarev/opower/alex-d-bondarev/learn-hadoop` to your project directory

Run in terminal:
`docker run \
 --hostname=quickstart.cloudera \
 --privileged=true \
 -t \
 -i  \
 -p 8888:8888 \
 -p 7180:7180 \
 -p 80:80 \
 -p 50070:50070 \
 -v /Users/oleksandrbondarev/opower/alex-d-bondarev/learn-hadoop:/home/cloudera \
 -w /home/cloudera \
 cloudera/quickstart \
 /usr/bin/docker-quickstart`
 
Once finished your terminal automatically attaches to the container.

## Step 4 - Prepare for Map Reduce job (word count)
- `cd /home/cloudera/target` 
- `echo "this is a simple document having simple text to count how many words it has" > test`
- `su hdfs` 
- `hdfs dfs -mkdir -p /user/cloudera/input/wc`
- `hdfs dfs -mkdir -p /user/cloudera/output/wc`
- `hadoop fs -put ../target /user/cloudera/input/wc/test`

## Step 5 - Run Map Reduce job (word count)
`hadoop jar learn-hadoop-1.0-SNAPSHOT.jar org.learn.hadoop.Main /user/cloudera/input/wc/test/test /user/cloudera/output/wc/1`
 
## References:
- More about cloudera docker: https://www.cloudera.com/documentation/enterprise/5-6-x/topics/quickstart_docker_container.html
- Used these tutorials:
http://msoliman.me/2017/04/24/hadoop-inside-docker-the-easiest-way-in-5-minutes/
http://msoliman.me/2017/04/24/first-map-reduce-inside-intellij-with-docker-container/