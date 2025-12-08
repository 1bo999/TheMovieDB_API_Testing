pipeline {
    agent any
    tools {
        maven 'Maven3'
    }
    stages {
        stage('Run Test') {
            steps {
                bat "mvn clean test"
            }
        }
    }
}
