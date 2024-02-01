pipeline {
	agent any
	stages {
		stage('---clean---'){
			tools {
				maven 'maven_3.9.6'
			}
			steps {
				sh 'mvn --version'
				sh "mvn clean"
			}
		}
		stage('test') {
			tools {
				maven 'maven_3.9.0'
			}
			steps {
				sh 'mvn --version'
				sh "mvn test"
			}
		}
		stage('---package---'){
			tools {
				maven 'maven_3.8.5'
			}
			
			steps {
				sh 'mvn --version'
				sh "mvn package"
			}
		}
	}
	post {
		success {
			echo 'job was built successfully - update sent by github webhook'
		}
		failure {
			echo 'job was not build..it was failed - update sent by github webhook'
		}
	}
}
