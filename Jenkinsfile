pipeline {
 	// Clean workspace before doing anything
    deleteDir()

    agent { docker 'openjdk:8-jre' } 
	stages {
		stage ('Clone') {
			deleteDir()
			checkout scm
		}
		stage ('Build') {
			sh "echo 'shell scripts to build project...'"
		}
		stage ('Tests') {
			parallel { 
				stage('static') {
					sh "echo 'shell scripts to run static tests...'"
				}
				stage('unit') {
					sh "echo 'shell scripts to run unit tests...'"
				}
				stage('integration') {
					sh "echo 'shell scripts to run integration tests...'"
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
			sh "echo 'shell scripts to deploy to server...'"
		}
	}
}