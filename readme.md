# Ansible-Kubernetes - CIS hardened

## Purpose
The purpose of this playbook and roles is to install a vanilla Kubernetes cluster with OIDC enabled
with the Calico CNI and the VSphere CPI.

It is a vanilla `kubeadm` cluster that can be managed by `kubeadm` going forward, or for easy upgrades
you can use the `upgrade` playbook.

It uses official helm charts or manifests to install the VSphere CPI and Calico CNI.

## CIS Benchmark
It also meets the CIS Benchmark 1.9 except for the following

5.1.7 - Avoid use of system:masters group

The reason it doesn't meet this one is that we add an OIDC group, Admins, and bind it to the system:masters.
This is so that you can use the cluster right from the get go. It is expected that you, as the k8s admin,
will create appropriate RBAC roles.
