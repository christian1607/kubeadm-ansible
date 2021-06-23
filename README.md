
## Kubernetes Ansible Playbook

This ansible playbook allows you to provision a kubernetes cluster based on kubeadm.    





## Installation

### Requirement

- vagrant
- pc with at least 10gb ram and 8 cores

### Provision VM
    

```bash
    vagrant up
```

This will provision 2 worker vm and 1 master vm, check connection with the command below:

```bash
    ansible <IP> -m command -a "uptime"
```

### Create cluster
    
    
```bash
    ansible-playbook 01-install-kubernetes.yaml -i inventory/hosts
```