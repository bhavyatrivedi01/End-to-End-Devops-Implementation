# End-to-End-Devops-Implementation

1. containerize application
install docker
create multistage Docke image for desctroless image
reduced size and security

2. create kubernetes menifests
deployment.yaml
service.yaml
ingress.yaml - specify ingress class so that , speciied ingress controller( eg. nginx controller will watch for k8 cluster).

3. create EKS cluster
install kubectl
install aws cli
configure aws
create cluster

4. Generate the kubeconfig File
Once your CLI is authenticated, use the following command to automatically create a configuration file at ~/.kube/config. This file tells kubectl which cluster to talk to and how to log in.

aws eks update-kubeconfig --region <your-region> --name <your-cluster-name>

5. apply kubernetes menifests to run a pod under eks cluster
kubectl apply -f k8s/menifests/deployment.yaml
kubectl apply -f k8s/menifests/service.yaml
kubectl apply -f k8s/menifests/ingress.yaml

- to delete a pod - kubectl delete deployment go-web-app
  
6. before inmplementing ingress controller to manae the file , take a pause and check if the application is running properly under created cluster or not.
   for which , expose the application using node-port mode
   change service from cluster-ip to node-port

   

