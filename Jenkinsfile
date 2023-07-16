pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'build'
            }
        }
        stage('test') {
            steps {
                echo 'test'
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
        success {
            echo 'success'
        }
        failure {
             echo 'failure'
        }
    }
}