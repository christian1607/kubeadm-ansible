
## test connection vms

    ```bash
    ansible 192.168.0.71 -m command -a "uptime"
    ```



## Instalar

### Requirement

- vagrant
- pc with at least 10gb ram and 8 cores

### Provision VM
    

```bash
    vagrant up
```

This will provision 2 worker vm and 1 master vm, 

### Create cluster
    
    
```bash
    ansible-playbook 01-install-kubernetes.yaml -i inventory/hosts
```