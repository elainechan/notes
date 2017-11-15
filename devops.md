# DevOps Notes

## Foundational Terminology and Concepts

### Software Development Methodologies
* Waterfall - sequential
* Agile - lightweight
* Scrum - daily meetings
### Operations Methodologies
* ITIL - information technology infrastructure library
* COBIT - control objectives for information and related technology
### Systems Methodologies
* Lean
    * Value
    * Value Stream
    * Flow
    * Pull
    * Perfection
* Sources
    * Thinking in Systems - Donella Meadows
    * How Complex Systems Fail - Richard Cook
### Development, Release, and Deployment Concepts
* Version Control
    * commit
    * conflicts
    * pull request
    * cherry picking
* Test-Driven Development
* Application Deployment
* Continuous Integration
* Continuous Delivery
* Continuous Deployment
* Minimum Viable Product
### Infrastructure Concepts
* Configuration Management
* Cloud Computing
* Infrastructure Automation
    * Configuration drift
    * MTBF - mean time between failure
    * MTTR - mean time to repair
    * Availability = MTBF/ (MTBF + MTTR)
    * Capacity management
    * Snowflake server - configuration by manual changes
* Artifact Management
    * Dependency management - storing dependent artifacts
    * Pinning - locking down explicit version of artifact for an environment
    * Promotion - selecting specific version to move toward delivery
* System Provisioning
* Containers
### Cultural Concepts
* Retrospective
* Postmortem
* Blamelessness
* Organizational Learning

## Four Pillars of Effective Devops
### Collaboration
### Affinity
### Tools
### Scaling

## Tooling
### Automation
* On-demand
* Scheduled
* Triggered

### Testing
* Smoke testing
* Regression testing
* Usability testing
* A/B testing
* Blue-green deployment
* Canary process

### Monitoring
Process of tracking current state of systems and environment, 
checking whether they meet some predefined conditions of desired state.
* Metrics - collection of qualitative and quantitative measurements
* Logging - generation, filtering, recording, and analysis of events due to OS or software messages
* Alerting
    * Impact
    * Urgency
    * Interested party
    * Resources
    * Cost
* Events

### Tool List
* Chef
* Puppet
* Kibana
* Ansible
* Elasticsearch
* Deployinator
* Docker
* Kubernetes
* Jenkins
* cron
* boto
* fabric
* Nagios
* Cacti
* Ganglia
* Graphite
* Logstash
* CollectD
* StatsD
* ELK
* Elasticache
* DynamoDB
* Redshift
