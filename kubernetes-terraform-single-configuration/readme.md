# Terraform Kubernetes Single Configuration

The following configuration follows the tutorial https://learn.hashicorp.com/tutorials/terraform/aks?in=terraform/kubernetes replacing some data for a free account.

1.  Follow the steps of the tutorial until you do: 
```
git clone https://github.com/hashicorp/learn-terraform-provision-aks-cluster
```

2. Replace the default configuration by one valid for a free account:

In aks-cluster.tf replace red parameters by green parameters (location and vm_size) in "aks-cluster.tf" file.

![image](https://user-images.githubusercontent.com/5442722/167361548-7da92762-7e13-424a-b318-14b54cfd87c4.png)

3. Continue with the next steps of the tutorial from "Active Directory" until the end:

https://learn.hashicorp.com/tutorials/terraform/aks?in=terraform/kubernetes#create-an-active-directory-service-principal-account

4. Deploy a basic hello-world Spring Rest Service (you can build the project in the followin [link](https://github.com/mrodfuentes/sharing/tree/main/java-spring-rest-docker))

Download the yml files from https://github.com/mrodfuentes/sharing/tree/main/java-spring-rest-docker/deployment.

   4.1 Create namespace:
```
kubectl apply -f 001-rtest-namespace.yml
```
     
   4.2 Create deployment:
```
kubectl apply -f 005-rtest-deployment.yml
```
Check that the creation was fine by checking the Kubernetes dashboard 

![image](https://user-images.githubusercontent.com/5442722/167366941-c71a6d61-a4ce-4546-ab49-75cb298d2e68.png)

Click on "workloads"

![image](https://user-images.githubusercontent.com/5442722/167367118-70b137e3-e0a2-414e-b09a-2077c6e00cfb.png)

You should see the deployment as follows (in red):

![image](https://user-images.githubusercontent.com/5442722/167367324-81fc0264-923d-4fa5-b712-1df356b6d744.png)

   4.3 Create service
```
kubectl apply -f 010-rtest-service.yml
``` 
Check the service is up by clicking on services section:

![image](https://user-images.githubusercontent.com/5442722/167368271-29772aed-64fe-4603-847f-f5bb32ea1fd3.png)

- Copy the link of the External IP and rewrite the URL to http://[IP]/greeting.
- Paste the link in a browser and you should see the following page:

![image](https://user-images.githubusercontent.com/5442722/167368732-3c29ccec-2c3b-401c-bfc6-5911f346babe.png)

Then, you can see the REST API deployed on the Azure Kubernetes Cluster.









