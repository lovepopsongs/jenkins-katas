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
              image 'gradle6.9:jdk11'
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