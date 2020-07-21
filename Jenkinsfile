pipeline {

    agent any

    stages {
        stage('Checkout') {
            steps { //Checking out the repo
                git 'https://github.com/kaitus/spring-boot-api-example.git'
            }
        }
		stage('compile') {
            steps { //Compile
                sh 'gradlew assemble'
            }
        }
        
		stage('Test') {
            steps {
                sh 'gradlew test'
            }
        }
    }
}
