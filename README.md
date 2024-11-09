# Azure DevOps CICD Pipeline Project

## Environment

### Virtual Machine

- create ubuntu VM. Name the user *devops_user*. Generate *devops_key.pem* file

- with PuttyGen, convert it into a *devops_key.ppk* file

- with Putty, set up the key file before connecting
<img src="/pictures/putty.png" title="putty"  width="900">
<img src="/pictures/putty1.png" title="putty"  width="900">

- run the commands
```
sudo chmod 666 /var/run/docker.sock
docker run -d --name sonar -p 9000:9000 mc1arke/sonarqube-with-community-branch-plugin:lts
```

### Agent Pool

- create agent pool




