pipeline{
	agent any
	environment {
		PROJECT_ID = "ordinal-rig-361104"
		CLUSTER_NAME = "cluster-1"
		LOCATION = "us-central1-c"
		CREDENTIALS_ID = "5c838932dd1530c4beb134acadcb71b09f14d073"
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
				sh "sed -i 's/tagversion/${BUILD_NUMBER}/g' simple.yaml"
				step([$class: 'KubernetesEngineBuilder', 
					projectId: env.PROJECT_ID, clusterName: env.CLUSTER_NAME,
					location: env.LOCATION, manifestPattern: 'simple.yaml', credentialsid: env.CREDENTIALS_ID,
					verifyDeployments: true
				])
			}
		}
		
	}
}