pipeline {

    agent any

    stages {
        stage('Checkout') {
            steps { //Checking out the repo
                git 'https://github.com/kaitus/spring-boot-api-example.git'
            }
        }
	stage('compile') {
            steps { //Compile application
                bat 'gradlew assemble'
            }
        }
	stage('deploy') {
            steps { //build application
                bat 'gradlew build'
            }
        }
	stage('run') {
            steps { //run application
                bat 'gradlew run'
            }
        }
        
	stage('Test') {
            steps {
                bat 'gradlew test'
            }
        }
    }
    post {
        always {
            junit 'build/test-results/**/*.xml'
        }
    }
}
