#GROUND UP BUILD OF MESOS ON UBUNTU

FROM ubuntu:14.04
MAINTAINER nrshrivatsan@outlook.com

#Updating Ubuntu
RUN apt-get update && apt-get -y install software-properties-common

#INSTALLING MESOS BINARY REQUIREMENTS
RUN add-apt-repository ppa:openjdk-r/ppa -y
RUN apt-get update && apt-get install -y openjdk-8-jdk autoconf libtool build-essential python-dev python-boto libcurl4-nss-dev libsasl2-dev maven libapr1-dev libsvn-dev git wget curl nano

#SETTING UP JAVA 8
RUN update-alternatives --set java /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java

#MOVING TO DIRECTORY FOR INSTALL MESOS
WORKDIR /usr/local/etc/

#CLONING GIT CODE
RUN git clone https://git-wip-us.apache.org/repos/asf/mesos.git

#MOVING TO DIRECTORY FOR BUILDING MESOS
WORKDIR /usr/local/etc/mesos
RUN ./bootstrap
RUN mkdir build
WORKDIR /usr/local/etc/mesos/build
RUN ../configure

#MAKING MESOS
RUN make -j 4

#EXPOSING PORTS
EXPOSE 5050
EXPOSE 5051
EXPOSE 2181


#INSTALLING AURORA
RUN apt-get install -y gradle
WORKDIR /usr/local/etc/
RUN git clone http://git-wip-us.apache.org/repos/asf/aurora.git
WORKDIR /usr/local/etc/aurora
RUN ./gradlew distZip


#RUNNING MESOS
CMD ["/usr/local/etc/mesos/build/bin/mesos-master.sh","--work_dir=/var/lib/mesos"]
