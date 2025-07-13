pipeline {
  agent any
  environment {
    ANYPOINT_CREDENTIALS = credentials('anypoint-exchange-rc')
  }
  stages {
    stage('Checkout') {
      steps {
        git credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/rrc09/cicd-demo'
      }
    }
    stage('Build & Deploy') {
      steps {
        sh 'mvn clean deploy -DmuleDeploy -s settings.xml'
      }
    }
  }
}