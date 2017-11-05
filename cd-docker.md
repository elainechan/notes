Stefana Muller
@stefanamuller
github.com/stefana912

VCTR - tool for scanning containers and VMs
problem: needed to write deployment script for 20 containers (not supposed to)
green field apps (new apps on docker)

easy:
packagint app into containers
test and QA
create images
hard:
deploy (10,000 lines of code)

Skopos - visual deployment system

deployment scripts issues:
one-way procedural streams
must change when app/arch changes
doesn't account existing state
multifaceted changes (deploy, upgrade, teardown)
no error handling (debugging)
no transparency on what's running now
prescriptive not descriptive (pipeline)
does not react/respond
are not features

deployment system requirements:
integrates with tool chain elems and existing management sys
recognizes code and arch updates
identify and respect dependencies: start-order, statefulness
auto deploys authed updates
auto corrects common errors, returns to proper op
provides meaningful logs and error msgs for integrated troubleshooting
operates from UI, CLI, API, or autonomously

[More](https://opsani.com/dockermeetup)

docker demo app cats dogs


