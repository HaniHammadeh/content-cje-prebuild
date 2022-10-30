pipeline {
  agent any
  stages {
    stage('Example Build') {
      agent any
      steps {
        echo 'Hello, Maven'
        sh 'uname -a'
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
            sleep 15
            sh '''echo I am $BUZZ
chmod +x ./bin/test_all.sh
./bin/test_all.sh'''
            archiveArtifacts(fingerprint: true, artifacts: 'traget/**')
          }
        }

      }
    }

  }
  environment {
    BUZZ = 'BUZZY'
  }
}