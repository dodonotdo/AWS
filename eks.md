## AWS Cluster creation 

Create a **`EKS cluster`**
- After creating the eks cluster, we need to run the below command on our local machine
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
