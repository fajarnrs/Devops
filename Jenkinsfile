pipeline{
	agent none
	// }
	// environment{
	// 	dockerhub=credentials('dockerhub')
	// }
	
	stages{
		stage("Build image"){
			steps{
				sh 'docker build -t simple-app:${BUILD_NUMBER} webapp/.'
			}
		}
		stage("Pushing to Docker hub"){
			steps{
				echo("Hello Deploy")
			}
		}
		stage("Deploy"){
			steps{
				echo("Hello Deploy")
			}
		}
		
	}
}