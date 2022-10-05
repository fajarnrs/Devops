pipeline{
	environment {
		registry = "fajarnrs/simpleservice"
		registryCredential= 'dockerhub_id'
	}
	agent any
	stages{
		}
		stage("Build image"){
			when{
				branch "main"
			}
			steps{
				sh 'docker build -t simple-app:${BUILD_NUMBER} webapp/.'
			}
		}
		stage("Pushing to Docker hub"){
			when{
				branch "main"
			}
			steps{
				sh 'docker tag simple-app:${BUILD_NUMBER} fajarnrs/simpleservice:${BUILD_NUMBER}'
				docker.withRegistry( '', registryCredential ) {
					dockerImage.push()
				}
			}
		}
		stage("Deploy"){
			steps{
				echo("Hello Deploy")
			}
		}
		
	}
}