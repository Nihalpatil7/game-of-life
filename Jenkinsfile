pipeline {
	agent {
		label {
			label "built-in"
		}
	}
	stages {
		stage ("maven-package") {
			steps {
				sh "mvn clean install"
			}
		}
		stage ("game-of-life-deploy") {
			steps {
				sh "ansible-playbook test.yaml"
			}
		}	
	}
}
