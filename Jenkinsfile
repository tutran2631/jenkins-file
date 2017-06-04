pipeline {
  agent any
  environment {
    archiveLocation = '/Users/trant/archives'
  }
  stages {
    stage('init') {
        steps {
            script {
                env.DEPLOY_CHOICES = sh(script: "ls -t $archiveLocation/*gz | sed -e 's/\..*$//'", returnStout: true)
                env.ENV_CHOICES = ["QA","DEV","BETA","PROD"].join("\n")
            }
        }
    }
    stage('params') {
        steps {
            script {
                def userInput = input(
                 id: 'userInput', message: 'Let\'s promote?', parameters: [
                 [$class: 'ChoiceParameterDefinition', choices: "$ENV_CHOICES", description: 'Environment', name: 'env'],
                 [$class: 'ChoiceParameterDefinition', choices: "$DEPLOY_CHOICES", description: 'Target', name: 'target'],
                ])
                echo ("Env: "+userInput['env'])
                echo ("Target: "+userInput['target'])
                env.DEPLOY_ENV = userInput['env']
                env.DEPLOY_TARGET = userInput['target']
            }

        }

    }
    stage('echo') {
        steps {
            sh 'echo "$DEPLOY_ENV - $DEPLOY_TARGET"'

        }
    }
  }
}