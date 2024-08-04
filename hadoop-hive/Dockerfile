FROM apache/hadoop:3
# 下载并解压 HBase
RUN wget https://mirror.sjtu.edu.cn/apache/hive/hive-4.0.0/apache-hive-4.0.0-bin.tar.gz -P /tmp \
    && tar -xzf /tmp/apache-hive-4.0.0-bin.tar.gz -C /opt \
    && rm /tmp/apache-hive-4.0.0-bin.tar.gz

ENV HIVE_HOME /opt/apache-hive-4.0.0-bin
ENV PATH $HIVE_HOME/bin:$PATH

#Custom configuration goes here
ADD conf/hive-site.xml $HIVE_HOME/conf
ADD conf/beeline-log4j2.properties $HIVE_HOME/conf
ADD conf/hive-env.sh $HIVE_HOME/conf
ADD conf/hive-exec-log4j2.properties $HIVE_HOME/conf
ADD conf/hive-log4j2.properties $HIVE_HOME/conf
ADD conf/ivysettings.xml $HIVE_HOME/conf
ADD conf/llap-daemon-log4j2.properties $HIVE_HOME/conf

RUN schematool -dbType derby -initSchema