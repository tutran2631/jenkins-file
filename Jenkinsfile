pipeline {
  agent any
  stages {
    stage('params') {
        steps {
            script {
                def userInput = input(
                 id: 'userInput', message: 'Let\'s promote?', parameters: [
                 [$class: 'ChoiceParameterDefinition', choices: ["QA","DEV"], description: 'Environment', name: 'env'],
                 [$class: 'TextParameterDefinition', defaultValue: 'uat1', description: 'Target', name: 'target']
                ])
                echo ("Env: "+userInput['env'])
                echo ("Target: "+userInput['target'])
                env.DEPLOY_TAG1 = userInput['env']
                echo "$DEPLOY_TAG1"
            }

        }

    }
    stage('echo') {
        steps {
            sh 'echo "$DEPLOY_TAG - $DEPLOY_TAG1"'

        }
    }
  }
}