# Deploy-DotNet-WebApp
# Pipeline Architecture

![kubernetes-Netapp](https://github.com/danjelhysenaj-dev/Deploy-WebApp/assets/72606127/ba6119ae-c24c-4663-84c6-d9ff24f9953d)

# Pipeline Run
<img width="745" alt="image" src="https://github.com/danjelhysenaj-dev/Deploy-WebApp/assets/72606127/518a58e9-07e2-419c-9fdb-1bae90abb046">
<img width="752" alt="image" src="https://github.com/danjelhysenaj-dev/Deploy-WebApp/assets/72606127/e9bbca5c-cf06-47d6-a6d8-201c10827ecb">

 Now you will see after running the pipeline the creation of new image has been done successfully in ACR
 
![image](https://github.com/danjelhysenaj-dev/Deploy-WebApp/assets/72606127/6f552963-9fdb-4d83-a084-b60dbcd86a81)

After this process you need to connect to you Azure Kubernetes Service (AKS) where you need to check if the deployment was done properly:
![image](https://github.com/danjelhysenaj-dev/Deploy-WebApp/assets/72606127/159f2df3-03c9-4fe0-9b8c-c68817f42159)


# samplewebapp
ASP.NET Web application deployment on Azure Kubernetes Services

Azure Kubernetes Services:

Agenda:
	- ASP.NET Web application deployment on Azure Kubernetes Services
		through Azure DevOps CI/CD

Flow:

- ASP.NET Web application creation
	- DockerFile creation
- Push changes in Azure Repos (Along with DockerFile)
- Build and Push Image (ACR Repository)
- Deploy (AKS)
	- Creation of deployment.yml and service.yml files

Commands:

	This will allow to track new POD creation
---
	kubectl get pods --watch
---
 	We will then install the kubectl tool
---
	az aks install-cli --install-location=./kubectl
---

This allows kubectl to connect to the Kubernetes cluster

---
	az aks get-credentials --resource-group devopsdanjel-rg --name devopsdanjelAKS 
---
Pre-defined Variables:

$(Pipeline.Workspace)
	- The local path on the agent where all folders for a given build pipeline are created.
