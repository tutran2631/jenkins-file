pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'git@github.com:tutran2631/jenkins-build-test.git', branch: 'master')
      }
    }
    stage('archive') {
      steps {
        archiveArtifacts(onlyIfSuccessful: true, artifacts: 'README.md')
      }
    }
    stage('complete') {
      steps {
        echo ' This is the build tag: ${env.BUILD_TAG}'
      }
    }
    stage('print') {
      steps {
        catchError() {
          sh 'echo "${BUILD_TAG} - ${env.BUILD_TAG}"'
        }
        
      }
    }
  }
}