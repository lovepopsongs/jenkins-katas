pipeline {
  agent any
  stages {
    stage('hello') {
      parallel {
        stage('Parallel') {
          steps {
            sh 'echo "kk"'
          }
        }

        stage('Build') {
          agent {
            docker {
              image 'gradle:6.8.3-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}