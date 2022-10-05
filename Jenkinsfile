pipeline{
	agent none
		stage("Build image"){
			when{
				branch "main"
			}
			steps{
				sh 'docker build -t simple-app:${BUILD_NUMBER} webapp/.'
			}
		}
		stage("Pushing to Docker hub"){
			steps{
				echo("Hello ss")
			}
		stage("Deploy"){
			steps{
				echo("Hello Deploy")
			}
		}
		
	}
}