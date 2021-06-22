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

        stage('Test log') {
          steps {
            writeFile(file: 'logtestfile.txt', text: 'This is an automated log file')
          }
        }

      }
    }

    stage('Deploy') {
      when {
          branch 'main'
        }
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to Deploy ?', id: 'ok')
            echo 'Deploy message'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'logtestfile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromedriverPath = 'C:\\ProgramData\\chocolatey\\lib\\chromedriver\\tools\\chromedriver.exe'
  }
}
