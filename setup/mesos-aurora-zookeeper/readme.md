#TL;DR

To Run 

` docker run -it -p 5050:5050 -p 5051:5051 -p 2181:2181 nasuno/mesos-aurora:latest`

#NOTE

This folder is a copy of https://github.com/nasunom/mesos-aurora

Docker file needs clean-up. Ideally Mesos, Aurora & ZK+Exhibitor need to be independent containers.

This would ensure separation of concerns.
