pipeline {
  agent any
  stages {
    stage('cleanup') {
        steps {
            sh 'rm -rf jenkins-build-test'
        }
    }
    stage('checkout') {
      steps {
        sh 'git clone -b master --single-branch git@github.com:tutran2631/jenkins-build-test.git'
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