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
        stage('push') {
            steps {
                echo 'push'
            }
        }
        stage('prod') {
            steps {
                echo 'production'
            }
        }
    }
    post { 
        success {
            echo 'success'
        }
        failure {
             echo 'failure'
        }
    }
}