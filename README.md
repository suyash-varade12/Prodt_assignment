# Prodt_assignment
This repo consist of :
1. Monitoring of temporal Docker containers and temporal server using prom and grafama
2. kubernetes manifest files for deployment of temporal dashboard and temporal web ui
3. Temporal sample queries run on prometheun UI
4. Grafana visualization of Docker containers and temporal server metrics


- [Overview](#overview)

## Overview:

In this assignment i was asked to setup temporal dashboard and temporal and monitor the docker comntainers and temporal server metrics, where i asked to use eks or deploy for deployment i have used my local(not EKS) for deployment purpose and i have successfully deployed temporal server and temporal web ui which manifests are attached in the repo.


Steps followed for this assignment:

1. Setting up an Environment 

Launched an AWS EC2 instance and installed Docker.

Deployed Temporal Server using Docker Compose.

Verified Temporal Server and Web UI were running.



2. Monitoring of Docker containers

To monitor dockeer containers first i have ensured that all the target to be up on prometheus(endpoints).In addition to confirm that the temporal server is exposing metrics i have tried running sample queries on prometheus to check whether the temporal server, after ensuring that all the targets are up i have created a grafana dashboard for temporal server metrics visualization whereas for docker container visualization i have used a pre-defined dashboard of Docker.

list out all the running docker containers and check the ports and allow aws security groups to allow those ports which are there .


3. Set up worker and workflows
     as mentioned i have taken the smaple workflow and sample worker in python and then build an image for deployment of temporal worker and pushed it to dockerhub

4. Deploying Temporal Server on Kubernetes

To deploy temporal server on kubernetes i have used minikube and have written manifest for 
  a. Temporal-server-deployment
  b. temporal-server-svc
  c. temporal-web-ui-deploy.yml
  d. temporal-web-ui-svc.yml
  e. namespace.yml


5. Monitoring temporal server
       To check the connectivity(temporal server is generating the metrics or not ) i have first tried running some basic queries in prometheus ui search bar for verifying metrics generation.
       Queries i run in prometheus for testing:
               temporal_workflow_task_queue_poll_empty
               temporal_activity_completed
               temporal_activity_failed



6. Challenges faced
       While setting up temporal and temporal worker i have faced the problems that there was a problem in the postgres connecting it was not accepting connections then i inspected and after checking logs i fixed that then after setting up the worker and workflows i have tried sample workflows and workers but there was issues as i was using ec2 so there was lot changes need to be done.and also while exposing temporal metrics it was giving error then after logging i fixed the error and then it was successfully exposing the metrics.


What i knew about Temporal platform

It is s used for managing workflows – kind of like an advanced task scheduler.
It has a server and workers – the server handles workflows, and workers execute tasks.
It stores data in a database – but not all databases work (SQLite didn’t work for us!).
It exposes metrics – which we can monitor using Prometheus & Grafana.
It runs on Docker & Kubernetes – and setting it up properly takes some effort.





# PRODT_ASSIGNMENT  

This repository consists of:  
1. Monitoring of Temporal Docker containers and Temporal Server using Prometheus and Grafana.  
2. Kubernetes manifest files for deploying Temporal Dashboard and Temporal Web UI.  
3. Sample Prometheus queries for monitoring Temporal Server.  
4. Grafana visualizations for Docker containers and Temporal Server metrics.  

## Table of Contents  
- [Overview](#overview)  
- [Steps Followed](#steps-followed)  
  - [Step 1: Setting Up the Environment](#step-1-setting-up-the-environment)  
  - [Step 2: Monitoring Docker Containers](#step-2-monitoring-docker-containers)  
  - [Step 3: Setting Up Worker and Workflows](#step-3-setting-up-worker-and-workflows)  
  - [Step 4: Deploying Temporal Server on Kubernetes](#step-4-deploying-temporal-server-on-kubernetes)  
  - [Step 5: Monitoring Temporal Server](#step-5-monitoring-temporal-server)  
- [Challenges Faced](#challenges-faced)  
- [What I Knew About Temporal](#what-i-knew-about-temporal)  
- [Next Steps](#next-steps)  

---

## Overview  

In this assignment, I was asked to:  
- ✅ Set up **Temporal Server and Temporal Web UI**.  
- ✅ Monitor **Docker containers and Temporal Server metrics**.  
- ✅ Use **EKS or any Kubernetes deployment** (I used Minikube instead of EKS).  
- ✅ Successfully deploy **Temporal Server and Temporal Web UI**.  
- ✅ Provide **Kubernetes manifests** (attached in this repo).  

---

## Steps Followed  

### Step 1: Setting Up the Environment  

1. **Launched an AWS EC2 instance** and installed Docker.  
2. **Deployed Temporal Server using Docker Compose.**  
3. **Verified Temporal Server and Web UI** were running.  

---

### Step 2: Monitoring Docker Containers  

To monitor Docker containers:  
1. Ensured all **targets were up** in Prometheus (checked endpoints).  
2. Confirmed that **Temporal Server was exposing metrics** (tested sample queries in Prometheus).  
3. Created a **Grafana dashboard** for Temporal Server metrics.  
4. Used **a predefined Docker dashboard** for monitoring containers.  

### Step 3: Setting Up Worker and Workflows
     
     as mentioned i have taken the smaple workflow and sample worker in python and then build an image for deployment of temporal worker and pushed it to dockerhub

### Step 4: Deploying Temporal Server on Kubernetes

To deploy temporal server on kubernetes i have used minikube and have written manifest for 
  a. Temporal-server-deployment
  b. temporal-server-svc
  c. temporal-web-ui-deploy.yml
  d. temporal-web-ui-svc.yml
  e. namespace.yml


### Step 5: Monitoring Temporal Server
       To check the connectivity(temporal server is generating the metrics or not ) i have first tried running some basic queries in prometheus ui search bar for verifying metrics generation.
       Queries i run in prometheus for testing:
               temporal_workflow_task_queue_poll_empty
               temporal_activity_completed
               temporal_activity_failed



### Challenges faced
       While setting up temporal and temporal worker i have faced the problems that there was a problem in the postgres connecting it was not accepting connections then i inspected and after checking logs i fixed that then after setting up the worker and workflows i have tried sample workflows and workers but there was issues as i was using ec2 so there was lot changes need to be done.and also while exposing temporal metrics it was giving error then after logging i fixed the error and then it was successfully exposing the metrics.


What i knew about Temporal platform

It is s used for managing workflows – kind of like an advanced task scheduler.
It has a server and workers – the server handles workflows, and workers execute tasks.
It stores data in a database – but not all databases work (SQLite didn’t work for us!).
It exposes metrics – which we can monitor using Prometheus & Grafana.
It runs on Docker & Kubernetes – and setting it up properly takes some effort.  

