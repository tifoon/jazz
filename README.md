
# Problem
![JaaS - Logo](https://avatars3.githubusercontent.com/u/14323142?v=3&s=200)


Jenkins is used to build software in enterprise firms. Providing a 100% available, elastic and resource efficient Jenkins cluster is a challenge. Hence JaaS = Jenkins as a Service.

#Goal
JaaS when complete would be an API first installable with containers as first class citizens.

#Motivation

eBay had solved this problem https://youtu.be/VZPbLUJnR68 using Mesos. However Mesos's components are prone to failure and eBay's solution is not open sourced when this document was created.

This project would be an open source API first JaaS experience for enterprises to install and maintain, with following attributes

1. Elastic
2. Reliable
3. Efficient

## Elastic - How?

Using Mesos + Aurora to spin off Jenkins containers [Docker for now] with a click of a button

## Reliable - How?

MAZ (Mesos+Aurora+Zookeeper) would provide Jenkins Resilience
MAZ on Kubernetes will provide MAZ Resilience.

## Efficient - How?

If a Jenkins instance isn't building anything, it would be hibernated and the resources allocated to that instance would be re-purposed to spin off another.
