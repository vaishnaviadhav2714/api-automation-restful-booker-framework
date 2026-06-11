pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Install Newman') {
            steps {
                bat 'npm install -g newman'
                bat 'npm install -g newman-reporter-htmlextra'
            }
        }

        stage('Run API Tests') {
            steps {
                bat '''
                newman run collections\\Restful Booker API Testing Framework.postman_collection.json ^
                -e environments\\QA.postman_environment.json ^
                -r cli,htmlextra ^
                --reporter-htmlextra-export reports\\report.html
                '''
            }
        }
    }
}