pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'build'
                sh 'mvn  package'
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