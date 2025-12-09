pipeline {
    agent any

    tools {
        jdk 'JDK21'
        maven 'Maven3'
    }

    environment {
            ALLURE_RESULTS = "${env.WORKSPACE}/target/allure-results"
        }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/1bo999/TheMovieDB_API_Testing.git'
            }
        }

        stage('Run Test') {
            steps {
                // For Mac/Linux
                // sh 'mvn clean test'

                // For Windows
                bat 'mvn clean test'
            }
        }

        stage('Generate Allure Report') {
            steps {
                allure([
                    includeProperties: false,
                    jdk: '',
                    properties: [],
                    reportBuildPolicy: 'ALWAYS',
                    results: [[path: 'target/allure-results']]
                ])
            }
        }
    }
}