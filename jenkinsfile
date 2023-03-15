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
		stage ("copy") {
			steps {
				sh "docker cp /mnt/project/game-of-life/gaodlife-web/target/gameoflife.war np://usr/local/tomcat/webapps"
			}
		}
	
	}
}
