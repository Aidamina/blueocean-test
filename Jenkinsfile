pipeline {
 	// Clean workspace before doing anything
    
    //agent { docker 'openjdk:8-jre' } 
	stages {
		stage ('Clone') {
			steps {
				deleteDir()
				checkout scm
			}
		}
		stage ('Build') {
			steps {
				sh "echo 'shell scripts to build project...'"
			}
		}
		stage ('Tests') {
			parallel { 
				stage('static') {
					steps {
						sh "echo 'shell scripts to run static tests...'"
					}
				}
				stage('unit') {
					steps {
						sh "echo 'shell scripts to run unit tests...'"
					}
				}
				stage('integration') {
					steps {
						sh "echo 'shell scripts to run integration tests...'"
					}
				}
			}
		}
		stage('Example Test') {
			steps {
				echo 'Hello, JDK'
				sh 'java -version'
			}
		}
		stage ('Deploy') {
			steps {
				sh "echo 'shell scripts to deploy to server...'"
			}
		}
	}
}