flag = false

pipeline {
  agent any
  environment {
    VERSION = '88.93.12'
  }
  
  stages {
    stage('Build') {
      steps {
        echo 'Building version ${VERSION}'
        // Here you can define commands for your build
      }
    }
    stage('Test') {
      when {
        expression {
          flag == false
        }
      }
      steps {
        echo 'Testing..'
        // Here you can define commands for your tests
      }
    }
    stage('Deploy') {
      steps {
        echo 'Deploying....'
        // Here you can define commands for your deployment
      }
    }
  }
  post {
    // the conditions here will execute after build is done
    always {
      // this action will happen always regardless the result of the build
      echo 'Post Build condition running'
    }
    failure {
      // this action will happen only if the build fails
      echo 'Failed to build'
    }
  }
}
