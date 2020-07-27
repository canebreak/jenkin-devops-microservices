pipeline {

	//agent { docker { image 'maven:3.6.3'} }
	//agent { docker { image 'node:13.8'} }
	agent any
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	
	stages {
		stage("Build")
		{
			steps {
				//sh "node --version"
				sh "mvn --version"
				sh "docker version"
				
				echo "BUILD ID - $env.BUILD_ID"
				echo "JOB NAME - $env.JOB_NAME"
				echo "BUILD TAG - $env.BUILD_TAG"
				echo " BUILD URL -$env.BUILD_URL"

			}
		}
		stage("Test")
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
 