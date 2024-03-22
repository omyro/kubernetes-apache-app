# Kubernetes Apache Project

## Initial Setup:

**Setting up kubectl on macOS**

I used the official [Kubernetes Documentation](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/#install-kubectl-on-macos) to install kubectl.

Next, I installed eksctl on macOS:
[eksctl](https://eksctl.io/installation/)

Check that both have been successfully installed by running the commands `kubectl version --client` and `eksctl version`.

![version1](images/version1.png)

![version2](images/version2.png)

Next, create a basic cluster using eksctl. Paste the following into the terminal:

```bash
eksctl create cluster \
> --node-type=t3.micro \
> --region=us-west-2 \
> --name=playground \
> --nodes=3 \
> --nodes-min=2 \
> --nodes-max=3
```

![createcluster](images/createcluster.png)

This will create a cluster with default settings (it will create the cluster in your default region in a default VPC, with one managed nodegroup with 2 m5.large nodes). If you'd like to include additional configurations, please visit the [eksctl official documentation website](https://eksctl.io/usage/creating-and-managing-clusters/).


![buildingstack](images/building.png)

![inprogress](images/inprogress.png)
 
![complete](images/complete.png)

![active](images/clusteractive.png)

It then creates a node group:

![nodegroup](images/nodegroup.png)

![nodeec2](images/nodeec2.png)
 
![playgroundready](images/ready.png)

`kubectl get nodes`
You don’t see the control plane, you only manage the nodes with AWS EKS

![getnodes](images/getnodes.png)


Deployment of the apache application with 2 replicas


![deployment](images/deployment.png)
 
![get](images/getdeploy.png)

![describe](images/describedeploy.png)

![getpods](images/getpods.png)

![describepod](images/describepod.png)

Creating LoadBalancer service, exposing application on port 80

 




Scaling the deployment:

 
