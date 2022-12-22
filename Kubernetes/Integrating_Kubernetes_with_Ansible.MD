# Integrating Kubernetes cluster with Ansible

1. Login to ansible server and copy public key onto kubernetes cluseter master account 

```sh
If an error occure when entering the command: "ssh-copy-id Username@Hostname" like the one below,
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/ubuntu/.ssh/id_rsa.pub"
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
ec2-user@18.218.249.98: Permission denied (publickey). For that, you should modify the ssh_config file at  PasswordAuthentication by changing his yes by no.
```

1. Update hosts file with new group called kubernetes and add kubernetes master in that. 

1. Create ansible playbooks to create **[deployment](https://github.com/yankils/Simple-DevOps-Project/blob/master/Kubernetes/kubernetes-valaxy-deployment.yml)** and **[services](https://github.com/yankils/Simple-DevOps-Project/blob/master/Kubernetes/kubernetes-valaxy-service.yml)** 
		
1.  Check for pods, deployments and services on kubernetes master
    ```sh 
    kubectl get pods -o wide 
    kubectl get deploy -o wide
    kubectl get service -o wide
    ```
	
1. Access application suing service IP
   ```sh
   wget <kubernetes-Master-IP>:31200
   ```
