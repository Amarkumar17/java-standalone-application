pipeline {
	agent any

    stages {
        stage('Build') {
			sh "mvn clean install"
        }
        stage('Run Application') {
			sh "java -cp target/java-standalone-application-1.0-SNAPSHOT.jar com.expertszen.App"
        }
        stage('Test') {
			sh "mvn test"
            post {
				always {
					junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
