#GROUND UP BUILD OF MESOS ON UBUNTU

FROM ubuntu:14.04.2
MAINTAINER nrshrivatsan@outlook.com

#Updating Ubuntu
RUN apt-get update

#INSTALLING MESOS BINARY REQUIREMENTS
RUN apt-get install -y openjdk-7-jdk autoconf libtool build-essential python-dev python-boto libcurl4-nss-dev libsasl2-dev maven libapr1-dev libsvn-dev git wget curl nano

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

#RUNNING MESOS
CMD ["/usr/local/etc/mesos/build/bin/mesos-master.sh","--work_dir=/var/lib/mesos"]
