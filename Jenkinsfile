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
        sh '''
            tar cvfz "$BUILD_TAG.tar.gz" jenkins-build-test
            cp "$BUILD_TAG.tar.gz" ~/archives/
        '''
      }
    }
    stage('complete') {
      steps {
        sh 'echo "Build tag: [${BUILD_TAG}]. Build id: [${BUILD_ID}]. Build Number: [$BUILD_NUMBER]. Build URL: [$BUILD_URL]"'
      }
    }
  }
}