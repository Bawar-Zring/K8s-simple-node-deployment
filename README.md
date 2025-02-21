# K8s-simple-node-deployment
Creating simple node.js app, deployment in K8s minikube cluster
                                   
  --------------------------------------------------------------------------------------------
in this reop i create deployment.yaml & service.yaml file for deployment, using Kubernetes

  ------------------------------------------------------------------------------------------------------
How to run it:
- check your minikube run:
  
  minikube status
- if not:
  
  minikube start
- run this command to apply both yaml file:
  
  kubectl apply -f deployment.yaml -f service.yaml
- get the url for accessing it:
  
  minikube service node-service
- in browser check /error endpoint, by accessing it the Node-App will crash, after some time K8s automatically will restart Node-App pod:
  
  http://127.0.0.1:[portNumber]/error
- also you can see the deployment, service and pods... etc. in K8s web dashboard:
  
  minikube dashboard

  -----------------------------------------------------------------------------------------------------------
- in case my image not availabe in docker hub any more, you can build it by you self:
  
  docker build -t [your-dockerhub-username]/[image-name]:[tag] .
- then push the image to you docker hub, remember to change the container image in deployment.yaml file to [your-dockerhub-username]/[image-name]:[tag]:
  
  docker push [your-dockerhub-username]/[image-name]:[tag]
  
