# Ansible-Kubernetes - CIS hardened

## Purpose

The purpose of this playbook and roles is to install a vanilla Kubernetes cluster with OIDC enabled
with the Calico CNI and the VSphere CPI.

It is a vanilla `kubeadm` cluster that can be managed by `kubeadm` going forward, or for easy upgrades
you can use the `upgrade` playbook.

It uses official helm charts or manifests to install the VSphere CPI and Calico CNI.

It installs HAProxy and Keepalived on the proxy nodes, this is needed for high availability of the cluster's
control plane.

## CIS Benchmark

Review the `hardening.md` to see the status of each benchmark test. Most of them were handeled out of the box
by kubeadm, the ones that could be resolved are.
