
## test connection vms

    ```bash
    ansible 192.168.0.71 -m command -a "uptime"
    ```



## 

    ansible-playbook 01-install-kubernetes.yaml -i inventory/hosts -e force_reset=true -v 
