pipeline {
  agent any
  tools {
    maven 'Maven'
  }
  parameters {
    choice (name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description:'version to deploy on production')
    booleanParam(name: 'executeTests', defaultValue: false, description: 'to run test cases')
  }
  
  environment {
    VERSION = '88.93.12'
  }
  
  stages {
    stage('Build') {
      steps {
        echo "Building version ${VERSION}"
        bat "npm --version"
        // Here you can define commands for your build
      }
    }
    stage('Test') {
      when {
        expression {
          params.executeTests
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
