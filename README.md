# OpenEBS

[![Build Status](https://travis-ci.org/openebs/jiva.svg?branch=master)](https://travis-ci.org/openebs/jiva)
[![Docker Pulls](https://img.shields.io/docker/pulls/openebs/jiva.svg)](https://hub.docker.com/r/openebs/jiva/)
[![Slack](https://img.shields.io/badge/chat!!!-slack-ff1493.svg)]( https://openebsslacksignup.herokuapp.com/)

http://www.openebs.io/
 
OpenEBS enables the use of containers for mission critical, persistent workloads.  OpenEBS is containerized storage and related storage services.   
 
OpenEBS allows you to treat your persistent workload containers, such as DBs on containers, just like other containers.  OpenEBS itself is deployed as just another container on your host, and enables storage services that can be designated on a per pod, application, cluster or container level, including:   
- Data persistence across nodes, dramatically reducing time spent rebuilding Cassandra rings for example
- Synchronization of data across availability zones and cloud providers
- Use of commodity hardware plus a container engine to deliver seriously scale out block storage
- Integration with orchestrators, so that developer and application intent flows into OpenEBS configurations automatically
- Management of tiering to and from S3 and other targets
- Plus we are bringing our experience from BSD based containerization and delivering QoS for customers from our CloudByte experience over to OpenEBS - expect to see more intelligence and manageability 
  
Our vision is simple: let us let storage and storage services for persistent workloads be so fully integrated into the environment and hence managed automatically that it almost disappears into the background as just yet another infrastructure service that works.  
 
## Why OpenEBS Scales
 
OpenEBS can scale to include an  arbitrarily large number of containerized storage controllers. Thanks in part to some advancements in the metadata management which removes a common bottleneck to scale out storage performance. Again, we have learned the hard way over the years at CloudByte and are extremely happy to see initial scale out performance figures with OpenEBS; much credit goes to the orchestration and containerization as well.
 
## Installation and Getting Started
 
OpenEBS can be setup in very few and easy steps.  You can get going on your choice of Kubernetes cluster by having open-iscsi installed on the Kubernetes nodes and running the openebs-operator using kubectl. 

**Start the OpenEBS Services using Operator**
```
wget https://raw.githubusercontent.com/openebs/openebs/master/k8s/openebs-operator.yaml
kubectl apply -f openebs-operator.yaml
```
**Customize or use the Default storageclasses**
```
wget https://raw.githubusercontent.com/openebs/openebs/master/k8s/openebs-storageclasses.yaml
kubectl apply -f openebs-storageclasses.yaml
```
You could also follow our [QuickStart Guide](http://openebs.readthedocs.io/en/latest/getting_started/quick_install.html).

OpenEBS can be deployed on any Kubernetes cluster - either in cloud, on-premise or developer laptop (minikube). Please follow our [OpenEBS Setup](http://openebs.readthedocs.io/en/latest/install/install_overview.html) documentation. Also, we have a Vagrant environment available that includes a sample Kubernetes deployment and synthetic load that you can use to simulate the performance of OpenEBS. 

 
## Status
We are approaching beta stage with active development underway. See our [Project Tracker](https://github.com/openebs/openebs/wiki/Project-Tracker) for more details.
 
## Contributing
 
We welcome your feedback and contributions in any form possible.  
 
Please join us on Slack at:  https://openebs-community.slack.com/
 
- Join us at [openebs-slack-signup](https://openebsslacksignup.herokuapp.com/)
  - Already signed up? Head to our discussions at [openebs-users channel](https://openebs-community.slack.com/messages/openebs-users/)
- Want to raise an issue?
  - If it is a generic (or `not really sure`), you can still raise it at [issues](https://github.com/openebs/openebs/issues)
  - Project specific issues can be raised at individual project level.
- Want to help with fixes and features?
  - Have a look at [open issues](https://github.com/issues?q=user%3Aopenebs+is%3Aopen)
  - Have a look at [contributing guide](./CONTRIBUTING.md)

## Show me the Code

This is a meta-repository for OpenEBS. Here, [openebs/openebs](https://github.com/openebs/openebs), please find various documentation related artifacts, e2e tests and code related to deploying OpenEBS with popular orchestration engines like Kubernetes, Swarm, Mesos, Rancher, and so on. The source code is available at the following locations:
- The core storage source code is under [openebs/jiva](https://github.com/openebs/jiva).
- The storage orchestration source code is under [openebs/maya](https://github.com/openebs/maya).
- While *jiva* and *maya* contain significant chunks of source code, some of the orchestration and automation code is also distributed in other repositories under the OpenEBS organization. 

Please start with the pinned repositories or with [OpenEBS Architecture](./contribute/design/README.md) document. 


## License

OpenEBS is developed under Apache 2.0 License at the project level. 
Some components of the project are derived from other opensource projects like Nomad, Longhorn 
and are distributed under their respective licenses. 
