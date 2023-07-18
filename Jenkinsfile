pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'build'
                sh 'mvn clean package'
            }
        }
        stage('test') {
            steps {
                echo 'test'
                sh 'mvn test'
            }
        }
        stage('UAT') {
            steps {
                echo 'UAT'
            }
        }
        stage('staging') {
            steps {
                echo 'staging'
            }
        }
        stage('prod') {
            steps {
                echo 'production'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success {
            echo 'success'
        }
        failure {
             echo 'failure'
        }
    }
}