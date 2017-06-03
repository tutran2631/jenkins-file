pipeline {
  agent any
  stages {
    stage('params') {
      steps {
          input(
               id: 'userInput', message: 'Let\'s promote?', parameters: [
               [$class: 'TextParameterDefinition', defaultValue: 'uat', description: 'Environment', name: 'env'],
               [$class: 'TextParameterDefinition', defaultValue: 'uat1', description: 'Target', name: 'target']
          ])
      }
    }
    stage('echo') {
        sh 'echo "$params.env"==="$params.target"'
    }
  }
}