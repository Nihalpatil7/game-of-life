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
		stage ("docker-compose") {
			steps {
				sh "cp /mnt/project/gameoflife-web/target/gameoflife.war /mnt/project/server/"
				sh "cp /mnt/project/dockerfile/docker-compose.yaml /mnt/project/"
			}
		}
		stage ("docker-compose-run") {
			steps {
				sh "docker-compose up -d"
			}
		}
	}
}
