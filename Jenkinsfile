pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'build'
                sh 'mvn  package'
            }
        }
        stages {
          stage("build & SonarQube analysis") {
            steps {
              withSonarQubeEnv('Sonar') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
        /*stage('UAT') {
            steps {
                echo 'UAT'
            }
        }
        stage('staging') {
            steps {
                echo 'staging'
            }
        }*/
        stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
              }
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