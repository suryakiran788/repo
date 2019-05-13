pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'hello'
            build(job: '123', propagate: true, quietPeriod: 2, wait: true)
          }
        }
        stage('action') {
          steps {
            node(label: 'asdfgh') {
              sh '''
ls -l'''
            }

          }
        }
      }
    }
    stage('test') {
      steps {
        retry(count: 10)
      }
    }
  }
}