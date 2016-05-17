# Docker Compose for Quick Start #

This compose file is the fastest way to get up and running with DivvyCloud.
All service dependencies are spun up with DivvyCloud as containers.

## Min Specs and pre-reqs## 
DivvyCloud requires atleast 6 Gigs of memory and 4 cores.
If using AWS, we recommend using a  m4.xlarge as a base spec for the quickstart system. 

docker-compose is also required for the DivvyCloud quickstart setup. 
Please see  https://docs.docker.com/compose/install/  for more information regarding docker-compose installation

## Setup ##

Once the system is up and running please sync down this repository.
All commands below assume your currenty working directory is the quickstart/ directory found in this repo. 


## First : Export registration variables ## 
The DivvyCloud docker setup looks for specific variables for automatic registration
Please make sure to export the following variables:
	- COMPANY_NAME
	- CONTACT_NAME
	- CONTACT_EMAIL

`
bash# export COMPANY_NAME=my_company
bash# export CONTACT_NAME=my_name
bash# export CONTACT_EMAIL=my_email
`

## Second : Start DivvyCloud using Docker Compose ##

`
docker-compose up -d
`

## Third : Please wait ... ## 

It will take DivvyCloud a few moments to initialize. 


## Last Step: ## 

Connect to in a web browser
http://[ip_address_of_system]:8001/

The first page you will see is a admin setup page. 

## Finally ## 

You are done .. enjoy divvycloud


### Quick Notes about CentOS w/ SE Linux] ###

SE Linux will prevent Docker from writing to the host system for persisting
MySQL and ElasticSearch data. The work around for this is :

`
  bash#  chcon -Rt svirt_sandbox_file_t esdata
  bash#  chcon -Rt svirt_sandbox_file_t db
`