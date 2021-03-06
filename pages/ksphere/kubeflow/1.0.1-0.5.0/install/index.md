---
layout: layout.pug
navigationTitle: Installation
title: Install KUDO for Kubeflow
menuWeight: 7
excerpt: Install KUDO for Kubeflow on your cluster
beta: false
enterprise: false
---

How do you want to deploy KUDO for Kubeflow?

You can install KUDO for Kubeflow:

- On public cloud infrastructure, such as Amazon Web Services (AWS), Microsoft Azure, or Google Cloud Platform (GCP).
- On a company-internal network with a physical (bare metal) or virtual infrastructure.
- On a company-internal network or VPC (virtual private cloud) without an internet connection: air-gapped/private/offline clusters.

The infrastructure you select determines the specific requirements for a successful installation.

## Prerequisites

- A Konvoy 1.5 cluster with the following addons enabled:
  - Istio
  - Knative
  - Kubeflow NFS
  Depending on whether you install KUDO for Kubeflow [on-premises](./on-premise) or in an [air-gapped](./air-gapped) environment, you have to follow the respective instructions.
- [`kubectl`](https://kubernetes.io/docs/tasks/tools/install-kubectl/) on your installation machine
- [KUDO CLI 0.15.0](https://kudo.dev/docs/cli/installation.html#cli-installation) plugin (remember to set `VERSION=0.15.0` if you use the instructions to `wget` from GitHub release page!)
