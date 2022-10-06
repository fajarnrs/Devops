pipeline{
	agent any
	environment {
		PROJECT_ID = "ordinal-rig-361104"
		CLUSTER_NAME = "cluster-1"
		LOCATION = "us-central1-c"
		CREDENTIALS_ID = "My First Project"
	}
	stages{
		stage("Build image"){

			steps{
				sh 'docker build -t simple-app:${BUILD_NUMBER} webapp/.'
			}
		}
		stage("Pushing to Docker hub"){
			steps{
				sh 'docker tag simple-app:${BUILD_NUMBER} fajarnrs/simpleservice:${BUILD_NUMBER}'
				withCredentials([usernamePassword(credentialsId: 'dockerhub_id', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]){
					sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
					sh 'docker push fajarnrs/simpleservice:${BUILD_NUMBER}'
				}
			}
		}
		stage("Deploy to GKE"){

			steps{
				sh "sed -i 's/simpleservice:v1/simpleservice:${BUILD_NUMBER}/g' simple.yaml"
				sh 'kubectl apply -f simple.yaml'
			}
		}
		
	}
}