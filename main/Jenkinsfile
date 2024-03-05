pipeline {
  agent any
  stages {
         stage('Clone repository') {
           steps {
               checkout([$class: 'GitSCM',
                branches: [[name: '*/main']],
                         userRemoteConfigs: [[url: 'https://github.com/pranathipraveen1402/PES1UG21CS428_Jenkins.git']]])
           }
         }
    stage('Build') {
      steps {
        build 'PES1UG21CS428-1'
        sh 'g++ main.cpp -o output'
      }
    }
    stage('Test') {
      steps {
        sh './output'
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy'
      }
    }
  }
  post{
    failure{
      error 'Pipeline failed'
    }
  }
}
