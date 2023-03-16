pipeline {
	agent {
		label {
			label "built-in"
			customWorkspace "/mnt/project"
		}
	}
	stages {
		stage ("mvn -install") {
			steps {
				sh "mvn install"
			}
		}
		stage ("git-clone") {
			steps {
				sh "git clone https://github.com/Nihalpatil7/dockerfile.git "
			}
		}
		stage ("docker-build") {
			steps {
				sh "cp /mnt/project/gameoflife-web/target/gameoflife.war /mnt/project/"
				sh "docker build -t test:1.0 /mnt/project/dockerfile/"
			}
		}
		stage ("docker-container") {
			steps {
				sh "docker run -itdp 8082:8080 --name np test:1.0"
			}
		}
	}
}
