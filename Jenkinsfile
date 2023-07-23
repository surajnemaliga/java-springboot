pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'build'
                sh 'mvn  package'
            }
        }
          stage("build & SonarQube analysis") 
          {
            steps {
              withSonarQubeEnv('Sonar') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
          stage("Quality Gate") {
                steps {
                  timeout(time: 5, unit: 'MINUTES') {
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
