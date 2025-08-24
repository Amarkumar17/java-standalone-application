pipeline {
	agent any
	stages{
		stage("Clean Up") {
			steps {
				deleteDir()
			}
		}
		stage("Clone Repo"){
			steps {
				sh "git clone https://github.com/Amarkumar17/java-standalone-application.git -b pipeline1"
			}
		}
		stage("Build") {
			steps {
				dir("java-standalone-application")
				{
					sh "mvn clean package"
				}
			}
		}
		stage("Test") {
			steps {
				dir("java-standalone-application")
				{
					sh "mvn test"
				}
			}
		}
	}
}
