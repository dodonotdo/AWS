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

  # Execute the created cluster on our local
  aws eks update-kubeconfig --region (region-name) --name (cluster-name)
  
  # Get the cluster details
  kubectl config get-contexts
  
  # Switch into the specified cluster
  kubectl config use-context (cluster-name)
  
  # Get the node Details
  kubectl get nodes
  
  # Service details
  kubectl get svc
  kubectl get svc -o wide
  
  # pod details
  kubectl get pods
  ```
