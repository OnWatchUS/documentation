---
title: Deploy
sidebar: Docs
showTitle: true
---
## Introduction

We have many alternatives for this topic, for example:

1. Kubernetes <a href="https://kubernetes.io/" target="_blank">**K8s**</a>
2. AWS Elastic Container Service. <a href="https://aws.amazon.com/ecs/" target="_blank">**ECS**</a>
3. A Simple <a href="https://docs.docker.com/compose/" target="_blank">**docker-compose**</a> in a EC2 instances.
4. Legacy form, is approvisioning a server (EC2 for example) manually and deploy the app inside,
   installing all dependences, the Capacity of system requires a Vertical Scalling (High cost).


### The problem

We need to create a small services encapsulated in a docker image, if the idea of company is scale the product correctly and reuse the different components of the system. The most common characterics is here
<a href="https://www.reactivemanifesto.org/en" target="_blank">Reactive manifesto</a>

| Topics               | K8s    | ECS    | docker-compose  | Legacy form  |
|---                   |---     |---     |---              |---           |
|Responsive            | High   | High   | Medium          | High         |
|Resilient             |        |        |                 |              |
|Elastic               |        |        |                 |              |
|Message driven        |        |        |                 |              |
|Debugging             |        |        |                 |              |
|**Initial Pricing**   | Medium | Low    | Low             | Low          |
|**Ending Pricing**    | Low    | Low    | Medium          | High         |
