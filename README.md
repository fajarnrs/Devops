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
             <img src=".screenshot/1.jpg" style="width:50px height:50px">
3. 



