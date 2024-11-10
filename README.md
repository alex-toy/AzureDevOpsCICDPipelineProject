# Azure DevOps CICD Pipeline Project

## Environment

### Virtual Machine

- create ubuntu VM. Name the user *devops_user*. Generate *devops_key.pem* file. User *RSA SSH Format* format.
<img src="/pictures/ubuntu.png" title="putty"  width="900">

- with *PuttyGen*, convert it into a *devops_key.ppk* file

- with *Putty*, set up the key file before connecting
<img src="/pictures/putty.png" title="putty"  width="400">
<img src="/pictures/putty1.png" title="putty"  width="400">

#### Agent Pool

- in the VM, run the commands
```
sudo apt update
wget https://xxxxxxxxxxxxxxxxxxxxxxxxxx
chmod 666 xxxxxxxxx.tar.gz
```

- in the VM, create the agent pool
```
./config.sh
```

- url : provide devops organisation url (https://dev.azure.com/xxxxxxxxxxorganisation)

- generation of the token
<img src="/pictures/token.png" title="token"  width="900">
<img src="/pictures/token1.png" title="token"  width="900">
<img src="/pictures/token2.png" title="token"  width="900">

- agent pool : provide the name of agent pool

- agent name : provide the name of VM

- work folder : leave default

- check that the agent pool has been added
<img src="/pictures/token3.png" title="token"  width="900">

- make the VM online
```
./run.sh
```

#### Installation

- in the VM, run the commands
```
cd ~
sudo apt install openjdk-17-jre-headless -y
sudo apt install maven -y
sudo snap install trivy
```

- install sonarqube
```
sudo apt  install docker.io
sudo chmod 666 /var/run/docker.sock
docker run -d --name sonar -p 9000:9000 mc1arke/sonarqube-with-community-branch-plugin:lts
```

### Pipeline

- create 
<img src="/pictures/pipeline.png" title="pipeline"  width="900">
<img src="/pictures/pipeline1.png" title="pipeline"  width="900">
<img src="/pictures/pipeline2.png" title="pipeline"  width="900">
<img src="/pictures/pipeline3.png" title="pipeline"  width="900">

### Agent Pool

- in *Organization Settings*, add an agent pool
<img src="/pictures/agent.png" title="agent pool"  width="900">

- inside newly created agent pool, do all necessary steps to create new agent inside the VM. Use *wget* to download necessary files
<img src="/pictures/agent1.png" title="agent pool"  width="900">




https://www.youtube.com/watch?v=0knqjEp3coU&list=PLZaC2MLnjptMycqxGu_DL-3s_Bx4yky3P&index=29