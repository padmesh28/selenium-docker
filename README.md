root@VMUbuntu1:~/dockertest# cat Dockerfile
FROM ingtest:3.0
CMD  mkdir /opt/testcode
COPY GVLM_ATF-master-070aa5279bb81a24bf832a8eff3effc5ac0036f3.zip /opt/testcode/
RUN cd /opt/testcode/ && \
  unzip GVLM_ATF-master-070aa5279bb81a24bf832a8eff3effc5ac0036f3.zip
ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64/
CMD cd /opt/testcode/GVLM_ATF-master-070aa5279bb81a24bf832a8eff3effc5ac0036f3/ING_Auto/branches/Hybrid_VAM/ING && \
  mvn clean install

