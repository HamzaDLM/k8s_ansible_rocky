# Setup a K8S cluster using Rocky and Ansible

The following repo has 4 main Ansible components:

- initialize.yaml (install dependencies)
- controllers.yaml (setup controller nodes)
- workers.yaml (setup worker nodes)
- join.yaml (join nodes to cluster)
- reset.yaml (reset a VM)

## Pre-requisites

- Have ansible installed on local machine
- Setup SSH key pair with all VMs
- Update hosts file with proper IPs

## Dependencies Installation

## Install master nodes

:warning: Disabling swap apparently doesn't work and I needed to ssh and do it manually after `kubeadm reset -f`
maybe the placement is wrong ?

```
sudo swapoff -a
sudo sed -i '/ swap / s/^/#/' /etc/fstab
```

## Install worker nodes

## Join worker and master nodes
