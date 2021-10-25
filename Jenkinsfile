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
              image 'gradle:6-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

    stage('test') {
      parallel {
        stage('test') {
          agent any
          environment {
            aefa = '1'
          }
          steps {
            echo 'aefaef'
          }
        }

        stage('') {
          steps {
            echo 'hsrhsrh'
          }
        }

      }
    }

    stage('test2') {
      steps {
        echo 'aefaefaf'
      }
    }

  }
}