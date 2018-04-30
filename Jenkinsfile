pipeline {
  agent any
  stages {
    stage('Fetch Code') {
      steps {
        echo 'Fetching Code....'
      }
    }
    stage('Java Build') {
      parallel {
        stage('Build ') {
          steps {
            echo 'Building the code...'
          }
        }
        stage('Compile') {
          steps {
            bat 'javac App.java'
          }
        }
      }
    }
    stage('Execution') {
      parallel {
        stage('Deploy') {
          steps {
            echo 'Deploying the code...'
          }
        }
        stage('Execute') {
          steps {
            bat 'java App'
          }
        }
      }
    }
    stage('Report') {
      steps {
        echo 'Reports created..Success'
      }
    }
  }
}