
## Kubernetes Ansible Playbook

This ansible playbook allows you to provision a kubernetes cluster based on kubeadm.    


Any recommedation or contribution is always welcomed. 

## Installation

### Requirement

- centos7 vm (so far, ubuntu support comming soon)
- vagrant (optional, if you don't have other vms) 
- ansible

### Provision VM
    

```bash
vagrant up
```

This will provision 2 worker vm and 1 master vm, check connection with the command below:

```bash
    ansible <IP> -m command -a "uptime"
```

### Create cluster

Before executing the main command, it is important to check the host file out, you notice that the host file contains the structure about your cluster and global variables like pod_cidr, cri_socket. Thus you must change those values if you're not using the default vagrant file
    
Once you define your host file the next is to run the next command
     
```bash
ansible-playbook 01-install-kubernetes.yaml -i inventory/hosts
```