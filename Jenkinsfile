pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/LexJacob/flasking.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t lexeljacob/flask_app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u lexeljacob -p dckr_pat_s03HfbbIHnoXkljKqTznZHN_5Rs'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push lexeljacob/flask_app'
      }
    }

  }
}