pipeline {
  agent any
  stages {
    stage('📥 Checkout from GitHub') {
      steps {
        git credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/rrc09/cicd-demo'
      }
    }
    stage('📦 Build & Deploy to CloudHub 2.0') {
      steps {
        sh 'mvn clean deploy -DmuleDeploy'
      }
    }
  }
  post {
    success {
      echo '🟢 Deployment to CloudHub 2.0 completed successfully!'
    }
    failure {
      echo '🔴 Deployment failed. Check logs for details.'
    }
  }
}