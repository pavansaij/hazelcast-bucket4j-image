FROM hazelcast/hazelcast:4.2.2


ENV BUCKET4J_VERSION 6.3.0
ENV JCACHE_VERSION 1.1.0
ENV HZ_VERSION 4.2.2

ENV HZ_LIB $HZ_HOME/lib
RUN mkdir -p $HZ_LIB
WORKDIR $HZ_LIB

RUN echo $HZ_LIB

# Download jcache and bucket4j jars from maven repo.
ADD https://repo1.maven.org/maven2/com/hazelcast/hazelcast-all/$HZ_VERSION/hazelcast-all-$HZ_VERSION.jar $HZ_LIB

#Original server.sh expected all eternal libs to be in a folder set by the CLASSPATH env variable. This is misleading and captured here: https://github.com/hazelcast/hazelcast-docker/issues/45
ENV CLASSPATH $HZ_LIB

WORKDIR $HZ_HOME

# Run hazelcast
CMD ./server.sh
EXPOSE 5701
