pipeline{
	agent {
		node{
			label "linux && python"
		}
	}

	stages{
		stage("Build"){
			steps{
				echo("Hello Build")
			}
		}
		stage("Test"){
			steps{
				echo("Hello Test")
			}
		}
		stage("Deploy"){
			steps{
				echo("Hello Deploy")
			}
		}
		
	}
}