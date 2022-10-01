pipeline {
  agent any
  stages {
    stage('checkout code') {
      steps {
        git(url: 'https://github.com/jodiefostersarmy/blue_ocean_tutorial', branch: 'dev')
      }
    }

    stage('logging') {
      parallel {
        stage('logging') {
          steps {
            sh 'ls -al'
          }
        }

        stage('front-end unit tests') {
          steps {
            sh 'cd curriculum-front $$ npm install -g && npm run test:unit'
          }
        }

      }
    }

  }
}