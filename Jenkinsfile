//Scripted

//Declarative
pipeline {
	    agent any
		environment {
			dockerHome = tool 'mydocker'
			mavenHome = tool 'mymaven'
			PATH = '$dockerHome/bin:$mavenHome/bin:$PATH'
		}
		//agent {docker {image 'maven:3.6.3'}} 
		//agent {docker {image 'node:13.8'}} 
		stages {
			stage('Build') {
				steps {
					sh "mvn --version"
					sh "docker --version"
			echo "Build"
			echo "$PATH"
			echo "BUILD NUM = $env.BUILD_NUMBER"
			echo "BUILD_ID=$env.BUILD_ID"
			echo "BUILD_TAG=$env.BUILD_TAG"
			//sh "node --version"
				}
			}
			stage('Test') {
				steps {
					echo "Test"
				}
			}
			stage('Integration Test') {
				steps {
							echo "Integration Test"
				}
			}

		}
		post {
			always {
				echo 'I run always'
			}
			success {
				echo 'I run on success'
			}
			failure {
				echo 'I run on failure'
			}
		}
	
}
