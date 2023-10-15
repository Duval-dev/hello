pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            build 'build'
            junit 'exa'
          }
        }

        stage('') {
          steps {
            sh '''pipeline {
    agent any
    stages {
        stage(\'Test\') {
            steps {
                sh \'./gradlew check\'
            }
        }
    }
    post {
        always {
            junit \'build/reports/**/*.xml\'
        }
    }
}'''
            }
          }

        }
      }

    }
  }