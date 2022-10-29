pipeline {
  agent any
  stages {
    stage('Example Build') {
      agent any
      steps {
        echo 'Hello, Maven'
        sh 'mvn --version'
      }
    }

    stage('Example Test') {
      parallel {
        stage('Example Test') {
          agent any
          steps {
            echo 'Hello, JDK'
            sh 'java -version'
          }
        }

        stage('buzz') {
          steps {
            echo 'Buzz Buzz'
          }
        }

      }
    }

  }
}