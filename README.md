# kubearmor

# AZURE Kubernetes Automation

# Before start this excercise,you must have running Rocky linux 8 machine.

# Architecture

[![Watch the image](/images/policyworkflow.JPG)]



# AZURE VM
 - Create 1 Rocky Linux 8.5 machine in the AZURE Cloud Portal
 - Note that this will work only in 'Pay-As-You-Go' Subscription and not on Free Tier
 - Make sure you open RDP,http,8080 ports for this new linux AZURE VM or you can also open any port by using port*any
 - Have Mobaxterm/ Putty installed. ** Note: We can use the PowerShell also, but in realtime production environment, Mobaxterm is the best option when we try to work on a junk server and push to the PROD.

[![Watch the image](/images/4policy.JPG)]

# Steps

- Step 1:  Install AZURE CLI in Rocky Linux Virtual Machine
- Step 2:  First install docker in the local linux machine
- Step 3:  Download a sample application
- Step 4:  Test the sample application
- Step 5:  Deploy and use Azure Container Registry
- Step 6:  Install kubectl command 
- Step 7:  Deploy an Azure Kubernetes Service (AKS) cluster
- Step 8:  Run applications in Azure Kubernetes Service (AKS)
- Step 9:  Scale application in Azure Kubernetes Service (AKS)
- Step 10: Update the application in Azure Kubernetes Service (AKS)


#

# Step 1: Install AZURE CLI

- Add the azure CLI Repository keys
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```
- Configure the azure CLI Repository

```
sudo sh -c 'echo -e "[azure-cli]
name=Azure CLI
baseurl=https://packages.microsoft.com/yumrepos/azure-cli
enabled=1
gpgcheck=1
gpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/azure-cli.repo'
```
- Install Azure CLI

```
sudo yum install azure-cli -y
```

- Login and sync your Azure CLI (Linux machine) to your portal.azure.com account

```
az login
```

- Now your linux machine has been fully authenticated with AZURE login.  