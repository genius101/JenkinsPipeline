pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'THis is a build message'
          }
        }

        stage('Test') {
          steps {
            echo 'This is a test message'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy message'
      }
    }

  }
}