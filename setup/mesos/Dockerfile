FROM ubuntu:14.04.2
RUN apt-get update
RUN apt-get install -y openjdk-7-jdk autoconf libtool build-essential python-dev python-boto libcurl4-nss-dev libsasl2-dev maven libapr1-dev libsvn-dev git wget curl nano
WORKDIR /usr/local/etc/
RUN git clone https://git-wip-us.apache.org/repos/asf/mesos.git
WORKDIR /usr/local/etc/mesos
RUN ./bootstrap
RUN mkdir build
WORKDIR /usr/local/etc/mesos/build
RUN ../configure
RUN make -j 4
CMD ["/usr/local/etc/mesos/build/bin/mesos-master.sh","--work_dir=/var/lib/mesos"]
