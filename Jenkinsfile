pipeline{
	agent any
	stages{
		stage('Maven Install'){
			agent {
				docker{
					image 'maven:3.5.0'
				}
			}
			steps{
				sh 'mvn clean install'
			}
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
				withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]){
					sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
					sh 'docker push fajarnrs/simpleservice:${BUILD_NUMBER}'
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