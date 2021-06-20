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
            echo "Get the Driver Path ${ChromedriverPath}"
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
  environment {
    ChromedriverPath = 'C:\\ProgramData\\chocolatey\\lib\\chromedriver\\tools\\chromedriver.exe'
  }
}