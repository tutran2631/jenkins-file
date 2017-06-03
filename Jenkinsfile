pipeline {
  agent any
  stages {
    stage('params') {
      steps {
        input(message: 'Please enter the build tag', id: 'DEPLOY_TAG', ok: 'OKDDD', submitter: 'submiter', submitterParameter: 'submitparam')
      }
    }
  }
}