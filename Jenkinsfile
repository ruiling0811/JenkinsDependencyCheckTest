pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/Desktop/3203/Project/Lab/JenkinsDependencyChecktest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
