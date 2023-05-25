# Installing A Kubernetes Bundle With Monitoring And CI/CD Pipelines Capabilities 
Overview

The increasing popularity of Kubernetes (K8s) attracts a growing number of first-time users seeking proper training. However, these users soon realize that to fully benefit from K8s, they need to incorporate other technologies alongside it. Consequently, the challenge for new users lies not only in studying K8s itself but also in familiarizing themselves with the broader K8s ecosystem, including various open-source software that interacts with it.

While there are numerous online resources covering each software individually, it is uncommon to find tutorials that guide users in setting up a cluster and integrating additional software into it. This repository aims to address this gap by providing instructions for setting up the following bundle:

A lightweight and scalable K3d cluster. K3d leverages Docker to create and manage Kubernetes multi-node clusters and is compatible with 'kubectl'.

Tekton, a Kubernetes-native CI/CD pipeline solution. The Kubernetes-native approach ensures tight integration with Kubernetes, enabling applications to fully leverage its powerful features, scalability, and resilience. Tekton's fundamental component is called "tasks" and is defined by YAML files.

Grafana, Prometheus, and Loki, which are lightweight, open-source monitoring solutions for real-time cluster monitoring. These monitoring tools are installed using Helm, which is a package manager for Kubernetes. Helm simplifies the deployment process through reusable YAML files known as "Helm charts" that can be pulled from Helm repositories.

A simple application interacting with MongoDB that is deployed to the cluster. This application provides data feeds for the monitoring and CI/CD pipeline components. This application is containerized, allowing it to be observable within the cluster.

There is a document provided in this repository (“Exploring Lightweight Kubernetes Clusters: Installation, Trends, and Implications”) which explains the full installation of this bundle in detail (section 5.2: The Installation Tutorial). 

Troubleshooting:

Since this bundle was selected for educational purposes with simplicity in mind, there weren't many issues encountered during the installation process. However, in a full-scale deployment, potential issues could arise. For instance, deploying too many Helm Charts simultaneously may lead to conflicts. This is because often charts depend on one another and if they are not executed in the right order, the deployment will be unsuccessful. Additionally, Tekton may encounter problems if YAML files have syntax issues or are not well defined.
In the scope of this tutorial, however, there exists a potential issue that is related to permissions granted to Tekton during the installation process. More details can be found in section 5.2 (The Installation Tutorial) of the report regarding this matter. 
