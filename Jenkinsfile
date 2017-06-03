pipeline {
  agent any
  stages {
    stage('params') {
      steps {
          def userPasswordInput = input(
                  id: 'Password', message: 'input your password: ', ok: 'ok', parameters: [string(defaultValue: 'master', description: '.....', name: 'LIB_TEST')]
              )
              echo ("Password was: " + userPasswordInput)
      }
    }
  }
}