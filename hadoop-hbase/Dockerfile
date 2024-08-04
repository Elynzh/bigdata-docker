# 使用 apache/hadoop:3 作为基础镜像
FROM apache/hadoop:3


# 下载并解压 HBase
RUN wget https://mirror.sjtu.edu.cn/apache/hbase/2.6.0/hbase-2.6.0-bin.tar.gz -P /tmp \
    && tar -xzf /tmp/hbase-2.6.0-bin.tar.gz -C /opt \
    && rm /tmp/hbase-2.6.0-bin.tar.gz

ENV HBASE_HOME /opt/hbase-2.6.0
ENV PATH $HBASE_HOME/bin:$PATH

# 配置 HBase
COPY conf/hbase-site.xml $HBASE_HOME/conf/hbase-site.xml
COPY conf/hbase-env.sh $HBASE_HOME/conf/hbase-env.sh
