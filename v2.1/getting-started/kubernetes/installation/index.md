---
title: Installing Calico on Kubernetes
---

Calico can be installed on a Kubernetes cluster in a number of configurations.  This document
gives an overview of the most popular approaches, and provides links to each for more detailed
information.

## Requirements

Calico can run on any Kubernetes cluster which meets the following criteria.

- The kubelet must be configured to use CNI network plugins (e.g `--network-plugin=cni`).
- The kube-proxy must be started in `iptables` proxy mode.  This is the default as of Kubernetes v1.2.0.
- The kube-proxy must be started without the `--masquerade-all` flag, which conflicts with Calico policy.
- The Kubernetes NetworkPolicy API requires at least Kubernetes version v1.3.0.

## [Calico Hosted Install](hosted)

Installs the Calico components as a DaemonSet entirely using Kubernetes manifests through a single
kubectl command.  This method is supported for Kubernetes versions >= v1.4.0.

## [Custom Installation](integration)

In addition to the hosted approach above, the Calico components can also be installed using your
own orchestration mechanisms (e.g ansible, chef, bash, etc)

Follow the [integration guide](integration) if you're using a Kubernetes version < v1.4.0, or if you would like
to integrate Calico into your own installation or deployment scripts.