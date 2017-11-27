# Deploying Apps 

## MERN CRUD App With ECS
* Building a NodeJS App with MongoDB Atlas and AWS Elastic Container Service.

* @jaydestro, Jay Gordon
* [Meetup talk](https://www.meetup.com/Docker-NewYorkCity/events/243339801/)
* [MERN CRUD Repo](https://github.com/jaydestro/mern-crud)

* ECS dev helper - [coldbrew cloud CLI](https://github.com/coldbrewcloud/coldbrew-cli)
* MERN app deploy on AWS ECS via coldbrew cloud
* MERN CRUD - real-time CRUD operations
* point-in-time backups
 
* M0 Atlas cluster
* role assign
* whitelist IP - host clusters, db cluster
* connection string config
* npm install
* npm start
 
* AWS environment variable
* aks - IAM key management
 
* create dockerfile
* create coldbrew.conf
* configure auto scaling
* coldbre cluster-create
* (no need for chef, terraform)
* coldbrew deploy
* builds image, test, push to ECS
* can use blue-green deployment to ELB endpoint
 
* coldbrew status
* when finish, can start provisioning

### Alternatives: 
* [Deployd](http://deployd.com/)
* [Deployinator by Etsy](https://github.com/etsy/deployinator)
---
## Continuous Deployment for Docker
* Stefana Muller
* @stefanamuller
* github.com/stefana912
 
* VCTR - tool for scanning containers and VMs
* problem: needed to write deployment script for 20 containers (not supposed to)
* green field apps (new apps on docker)
 
* easy:
* packagint app into containers
* test and QA
* create images
* hard:
* deploy (10,000 lines of code)
 
* Skopos - visual deployment system
 
* deployment scripts issues:
* one-way procedural streams
* must change when app/arch changes
* doesn't account existing state
* multifaceted changes (deploy, upgrade, teardown)
* no error handling (debugging)
* no transparency on what's running now
* prescriptive not descriptive (pipeline)
* does not react/respond
* are not features
 
* deployment system requirements:
* integrates with tool chain elems and existing management sys
* recognizes code and arch updates
* identify and respect dependencies: start-order, statefulness
* auto deploys authed updates
* auto corrects common errors, returns to proper op
* provides meaningful logs and error msgs for integrated troubleshooting
* operates from UI, CLI, API, or autonomously
 
* [More](https://opsani.com/dockermeetup)
 
* docker demo app cats dogs
