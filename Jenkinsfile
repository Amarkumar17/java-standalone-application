pipeline {
	agent any

    stages {
		stage('Build') {
			steps{
				sh "mvn clean install"
			}
        }
		stage('Test') {
			steps{
				sh "mvn test"
				}
            post {
				always {
					junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Run Application') {
			steps{
				sh "java -cp target/java-standalone-application-1.0-SNAPSHOT.jar com.expertszen.App"
			}
        }
    }
}
