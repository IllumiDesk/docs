---
description: Introduction to the IllumiDesk Enterprise Edition (EE).
---

# Introduction

The **IllumiDesk Enterprise Edition \(EE\)** is a **Kubernetes** application. You can install the software by attaching the IllumiDesk EE application to an existing cluster or use our installer that has an embedded, production-ready Kubernetes distribution packaged with it.

## Advanced Options

The install scripts are idempotent. Re-run the scripts with different flags to change the behavior of the installer.

| **Flag** | **Usage** |
| :--- | :--- |
| airgap | Do not attempt outbound Internet connections while installing. |
| ha | Install in multi-master mode. |
| load-balancer-address | IP:port of a load balancer for the K8s API servers in ha mode. |
| public-address | The public IP address. |
| installer-spec-file | This flag takes the path to a ‘patch’ yaml file. The config in this patch will be merged with the existing installer yaml, taking precedence where there is conflict, and will change the installation based on the final config. |
| preserve-docker-config | This flag will make the kURL installer keep the current docker config of the node, overriding any yaml config |
| preserve-selinux-config | This flag will make the kURL installer keep the current Selinux config of the node, overriding any yaml config. |
| preserve-firewalld-config | This flag will make the kURL installer keep the current Firewalld config of the node, overriding any yaml config. |
| preserve-iptables-config | This flag will make the kURL installer keep the current Iptables config of the node, overriding any yaml config. |

## Troubleshooting

IllumiDesk Enterprise has a built-in troubleshooting tool. On the admin console, click on the Troubleshoot tab, and you can download a support bundle. By default, this will run through a series of prebuilt analyzers to help identify potential issues. If you’re unable to remediate the issue you can deliver the support bundle to our support team, we can help identify any problems with your IllumiDesk Enterprise installation.

## Advanced Existing Cluster Installation

IllumiDesk Enterprise is packaged as a Kubernetes application that can run on any Kubernetes cluster that meets minimum requirements:

1. Kubernetes 1.16.0 or later \(although we recommend 1.18\)
2. A default storage class that can be used for relocatable storage
3. A single namespace that all of the IllumiDesk components will be deployed to
4. A standard ingress controller that can be accessed by the clients sending error reports

To verify that your cluster meets the minimum requirements, you can run our preflight checks before installing. To run the preflight checks on your cluster, run:

  
$ curl https://krew.sh/preflight \| bash

$ kubectl preflight https://illumidesk.intel.local/preflight  


This will not run anything in your cluster but will review your cluster version and resources and provide a summary to help you identify if the cluster meets the minimum or recommended requirements.

### View and apply Kubernetes manifests

If you’re unable or uncomfortable installing the admin console directly from kots, you can first pull the manifests that you’ll be deploying and kubectl apply those manifests. By default, these manifests are delivered with an empty kustomization.yaml in case you need to make last-mile configuration changes with kustomize.

  
 $ curl https://kots.io/install \| bash

 $ kubectl kots pull illumidesk-enterprise-&lt;release&gt; --license-file ~/path/Intel.yaml

###  Edit configuration locally

Using your favorite editor, open the file ~/illumidesk-enterprise/upstream/userdata/config.yaml, make any changes you need and save it, and then rerun **kots pull** to apply those changes to the deployable YAML manifest.

  
 $ kubectl kots pull illumidesk-enterprise-&lt;release&gt; --license-file ~/path/license.yaml

 $ kubectl apply -k ~/illumidesk-enterprise-&lt;release&gt;/overlays/midstream

###  Using an internal registry

If your cluster is unable to download images from external registries, you’ll also need to store the images in your internal registry. If your workstation has push access to that registry, Kots can download, retag, push those images on your behalf and prepare a YAML overlay with the new image location referenced.

  
 $ kubectl kots pull illumidesk-enterprise-&lt;release&gt; \

 --license-file ~/Intel.yaml \

 --rewrite-images \

 --image-namespace illumidesk-enterprise-&lt;release&gt; \

 --registry-endpoint https://&lt;vendor-specific-registry&gt;

This command will:

1. Download and store all manifests in ~/illumidesk-enterprise/upstream
2. Find all images referenced in all application manifests
3. Pull the images into ~/illumidesk-enterprise/images
4. Retag and push each image to the internal image registry
5. Add a kustomization patch to the kustomization.yaml in the midstream, changing all image names, but persisting your local configuration changes to the config.yaml

After this process has completed you can deploy the application leveraging the internal images by running:

  
 $ kubectl apply -k ~/illumidesk-enterprise/overlays/midstream

##  Automating Day-2 Operations

### Leverage 1st-party deployment pipelines

IllumiDesk Enterprise is designed to integrate with existing 1st-party deployment pipelines for customers who want to bring their internal image registry and/or manage YAML versioning in a version control system \(often called GitOps\).

### Deploying by GitOps

If you have a GitOps deployment pipeline \(good choice\), you can add that into the Admin Console and have every update be delivered as an automated git commit into your existing GitOps pipeline. This allows you to review the YAML before deploying, and also exposes a workflow for you to run IllumiDesk Enterprise in multiple environments to verify the updates before deploying to production.

#### **Leveraging an Internal Registry**

Once the IllumiDesk Admin Console is installed you can configure it so that IllumiDesk images will be retagged and pushed to your internal registry for further scanning, etc. YAML will be rewritten so that images will be pulled from the specified internal registry at runtime.

#### **Deploying to Multiple Clusters**

Once the IllumiDesk Admin Console is installed you can configure multiple clusters. Click “Clusters” to specify whether each cluster should be auto-deployed or GitOps-deployed.

#### **Storage**

Optionally, you can provide a Postgres server. If you choose to bring your own Postgres server, it should be at least Postgres 10.4. If you don’t bring your own, the installer will provision Postgres as a Stateful set in your cluster.

