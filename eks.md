## AWS Cluster Creation 

1. Create a **`EKS cluster`**

2. Install the kubectl setup on local machine - https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

3. Install the EKS cluster setup on local machine - https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

4. Configure the cluster details on local

`AWS IAM -> user -> security crentials -> generate access key`
```sh
# Credentials Configuration
aws configure
  - access key
  - secret key
  - region
  - output data format
 
# list the configuration details
aws configure list
```

5. After creating the eks cluster, we need to run the below command on our local machine
  ```sh
  # Check the aws credentials details
  aws eks describe-cluster --region (region-name) --name (cluster-name) --query cluster.status
```
  ![image](https://user-images.githubusercontent.com/91359308/208497024-017c613e-8def-462a-a85e-994b08d43f53.png)

  ```
  ```
**6. Added a new cluster on local**

 ```sh
  # Execute the created cluster on our local
  aws eks update-kubeconfig --region (region-name) --name (cluster-name)
 
  # Get the cluster details
  kubectl config get-contexts
  
  # Switch into the specified cluster
  kubectl config use-context (cluster-name)
  ```
  ![image](https://user-images.githubusercontent.com/91359308/208496869-6113a02c-addd-43d7-9493-475258b04ff5.png)
  
**7. svc details**
 ```sh
  # Service details
  kubectl get svc
  kubectl get svc -o wide
  ```
  ![image](https://user-images.githubusercontent.com/91359308/208496688-200dfbd6-d4f2-4a3e-b271-73da9ed16cdc.png)

**8. kubectl node details**
   ```sh
  # Get the node Details
  kubectl get nodes
  ```
![image](https://user-images.githubusercontent.com/91359308/208496466-a0748902-6443-415c-aad4-d2e7ea0aa9c8.png)

**9. kubectl pod**
  ```sh
  # pod details
  kubectl get pods
  ```


Note:
-----
Reference - https://www.youtube.com/watch?v=SsUnPWp5ilc
