pipeline {
  agent any
  stages {
    stage('Print message') {
      steps {
        echo 'Welcome to Jenkins !'
      }
    }

    stage('Add file') {
      steps {
        prependToFile(file: 'Test.txt', content: 'Testing.........................')
      }
    }

  }
}
