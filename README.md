# Devops Test New Employment

This is for Test Number 2 to deploy SimpleService and Influxdb

<h2>Tools Must Install Before Start</h2>
1. Jenkins
   <p> Install Plugin kubernetes, kubernetes CLI, Google Kubernetes Engine, Kubernetes Credential Plugin and make sure git plugin installed</p>
   <p>next step create credential in jenkins like credential for login to github repo, docker repo and google kubernetes</p>

2. Docker
    <p> After Install Docker Engine in Linux, Please Usermod first for running jenkins to docker 'usermod -aG docker jenkins'</p>
    <p>Restart Docker after usermod<p>
3. kubectl
4. google kubernetes engine

<h2>Jenkins Prepare CI/CD</h2>
1. Setting Node Cloud for Connect to Google Kubernetes Engine 'Manage Jenkins -> Manage Nodes and Clouds -> Manage Clouds'
2. Choose Kubernetes in 'kubernetes' you can assign kubernetes cluster IP from your GKE(Google Kubernetes Engine) Cluster and get Credential key sam place under IP kubernetes Cluster
            ![1](https://user-images.githubusercontent.com/75650288/194388335-b7f6d83c-41fd-4ab1-bc89-250082b75e22.jpg)
3. 



