# DevOps Test Documentation

## Table of Contents

1. [Introduction](#1-introduction)
2. [Kubernetes Cluster Setup](#2-kubernetes-cluster-setup)
   a. [Minikube Configuration](#a-minikube-configuration)
   b. [MySQL Configuration](#b-mysql-configuration)
   c. [PhpMyAdmin and WordPress Services](#c-phpmyadmin-and-wordpress-services)
   d. [Ingress Services](#d-ingress-services)
3. [Helm Chart for WordPress](#3-helm-chart-for-wordpress)
   a. [Helm Chart Configuration](#a-helm-chart-configuration)
   b. [Service Configuration](#b-service-configuration)
   c. [ConfigMap Configuration](#c-configmap-configuration)
   d. [Deployment Configuration](#d-deployment-configuration)
   e. [values.yaml](#e-valuesyaml)
4. [Helm Chart Details](#4-helm-chart-details)
5. [Conclusion](#5-conclusion)

---

## 1. Introduction

The purpose of this project is to set up a Kubernetes cluster on a single node and create a Helm Chart that bootstraps a WordPress application with MySQL and PhpMyAdmin ingress. The project name is 'DevOps Test.'

## 2. Kubernetes Cluster Setup

### a. Minikube Configuration

The Kubernetes cluster is set up using Minikube. Minikube simplifies the process of running a local Kubernetes cluster. The following steps were taken:

- Installation of Minikube on the VPS running Ubuntu 22.
- Configuration of Minikube to use a single node for the cluster.

### b. MySQL Configuration

For database storage, MySQL was configured with the following components:

- **MySQL Service:** This service defines how MySQL can be accessed within the cluster.
- **MySQL Secret:** It is used to securely store sensitive data like database passwords.
- **MySQL Storage Configuration:** Storage settings were defined for MySQL to ensure proper data storage and access.

### c. PhpMyAdmin and WordPress Services

The project includes the following services:

- **PhpMyAdmin Service (NodePort):** PhpMyAdmin is made available through a NodePort service, allowing for external access on a specific port.
- **PhpMyAdmin Service 2 (LoadBalancer):** Another PhpMyAdmin service is exposed as a LoadBalancer, providing access via a public IP address.
- **WordPress Chart (LoadBalancer):** WordPress is also configured as a LoadBalancer service for external access.

### d. Ingress Services

Ingress services were set up to allow external access to PhpMyAdmin and WordPress. These services are defined within the default namespace of Kubernetes.

## 3. Helm Chart for WordPress

### a. Helm Chart Configuration

- **Helm Chart Name:** wordpress-chart-v1
- **Repository:** Default

### b. Service Configuration

The Helm Chart includes a YAML file that defines the service configuration for WordPress. This file specifies how WordPress can be accessed within the cluster, including port settings and other service details.

### c. ConfigMap Configuration

A ConfigMap configuration file is included in the Helm Chart. This file contains various settings and configurations for WordPress. It can be customized to tailor WordPress to specific needs.

### d. Deployment Configuration

A YAML file for deployment is included in the Helm Chart. This file deploys the WordPress application within the Kubernetes cluster. It defines the desired state of the WordPress deployment, including replica counts and container specifications.

### e. values.yaml

The values.yaml file is an essential part of the Helm Chart. It contains configuration settings for the WordPress deployment, including database user, name, and password. These settings can be adjusted as needed during deployment.

## 4. Helm Chart Details

The Helm Chart named 'wordpress-chart-v1' is a valuable component for streamlining the deployment of WordPress within the Kubernetes cluster. It offers the following:

- Simplified service configuration for WordPress.
- Customizable settings through the ConfigMap and values.yaml files.
- Integration with the MySQL database configured in the project.

## 5. Conclusion

This document provides a detailed overview of the 'DevOps Test' project, explaining the setup of a Kubernetes cluster and the Helm Chart used for deploying WordPress. The Helm Chart simplifies deployment and offers flexibility in configuring WordPress settings.

