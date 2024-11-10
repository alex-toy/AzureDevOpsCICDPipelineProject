# Azure DevOps CICD Pipeline Project

## Environment

### Virtual Machine

- create ubuntu VM. Name the user *devops_user*. Generate *devops_key.pem* file. User *RSA SSH Format* format.
<img src="/pictures/ubuntu.png" title="putty"  width="400">

- with *PuttyGen*, convert it into a *devops_key.ppk* file

- with *Putty*, set up the key file before connecting
<img src="/pictures/putty.png" title="putty"  width="400">
<img src="/pictures/putty1.png" title="putty"  width="400">

- in the VM, run the commands
```
sudo chmod 666 /var/run/docker.sock
docker run -d --name sonar -p 9000:9000 mc1arke/sonarqube-with-community-branch-plugin:lts
```

### Pipeline

- create 
<img src="/pictures/pipeline.png" title="pipeline"  width="400">
<img src="/pictures/pipeline1.png" title="pipeline"  width="400">
<img src="/pictures/pipeline2.png" title="pipeline"  width="400">
<img src="/pictures/pipeline3.png" title="pipeline"  width="400">

### Agent Pool

- create agent pool




https://www.youtube.com/watch?v=0knqjEp3coU&list=PLZaC2MLnjptMycqxGu_DL-3s_Bx4yky3P&index=29