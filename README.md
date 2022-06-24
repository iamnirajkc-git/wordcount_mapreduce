# wordcount_mapreduce
make ec2 instance in AWS.
connect ec2 with puTTY using ssh key-generated.
Sudo -i     — switch to root
  1 yum update -y
  2  yum install java-1.8.0-openjdk -y
  3 amazon-linux-extras install java-openjdk11
  5 java -c
  6 java -version
  7 alternatives --config java - - switch version type number 2
  8 java -version — version switch to java 11.0.13
  9 wget https://dlcdn.apache.org/hadoop/common/hadoop-3.2.3/hadoop-3.2.3.tar.gz
  10 tar -xzvf hadoop-3.2.3.tar.gz
  11 mv hadoop-3.2.3 /usr/local/hadoop
  12 vi /etc/environment and add below lines. Pls remove any other text
      PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/usr/local/hadoop/bin:/usr/local/hadoop/sbin
"
JAVA_HOME=”/usr/lib/jvm/default-java”
  13 source /etc/environment
  15 vi wordcount   - - copy the content from word count.java
  17 export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.312.b07-1.amzn2.0.2.x86_64/jre
  19 hadoop jar /usr/local/hadoop/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.3.jar wordcount /usr/local/hadoop/LICENSE.txt ~/output
  20  cat ~/output/part-r-*  - - verify the output
