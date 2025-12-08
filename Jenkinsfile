pipeline {

tools {
    jdk 'JDK21'
    maven 'Maven-3.9'
}

stages {
    stage('Checkout') {
        git branch: 'main',
        url: 'https://github.com/1bo999/TheMovieDB_API_Testing.git'
    }

    stage('Run Test') {
        bat 'mvn clean test'
        }


    stage('Generate Allure Report') {
        allure([
             results: [[path: 'target/allure-results']]
        ])
        }

}


}