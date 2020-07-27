pipeline {

	//agent { docker { image 'maven:3.6.3'} }
	agent { docker { image 'node:13.8'} }
	stages {
		stage("Build")
		{
			steps {
				sh "node --version"
				//sh "mvn --version"
				echo "$env.BUILD_ID"
				echo "$env.JOB_NAME"
				echo "$env.BUILD_TAG"
				echo "$env.BUILD_URL"
			}
		}
		stage("Blagoje")
		{
			steps{
				echo "Test"
			}
		}

		stage("Integration Test")
		{
			steps{
				echo "Integration Test"
			}
		}
	}
	post{
		always{
			echo "I run always. I am awesome"
		}
		success {
			echo "I run when build is successful"
		}
		failure {
			echo "I run when build fail"

		}
		changed {
			echo "I run everytime when build status is changed"
		}
	}

}
 