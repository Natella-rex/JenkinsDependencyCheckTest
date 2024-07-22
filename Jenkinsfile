pipeline {
	agent any
	stages {
 		stage('Checkout SCM') {
 			steps {
 				git '/home/jenkins/agent/workspace/Lab 6/JenkinsDependencyCheckTest'
 			}
 		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '-n --noupdate --format HTML --format XML --suppression suppression.xml', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}

