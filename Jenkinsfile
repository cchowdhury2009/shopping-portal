pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'this is the build job'
            sh 'npm install'
          }
        }

        stage('archive') {
          steps {
            archiveArtifacts '**/distribution/*.'
          }
        }

      }
    }

    stage('test') {
      steps {
        echo 'this is the test job'
        sh 'npm test'
      }
    }

    stage('package') {
      steps {
        echo 'this is the package job'
        sh 'npm run package'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this is the pipeline for Shopping catrs...'
    }

  }
}