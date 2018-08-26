pipeline {
  agent any
  stages {
    stage('ST Deploy Phase') {
      steps {
        parallel(
          "App1 Build": {
            build 'MJ1'
            
          },
          "App2 Build": {
            build 'MJ2'
            
          }
        )
      }
    }
    stage('Confirmation Phase') {
      steps {
        input(message: 'Click "Proceed" to Continue', ok: 'Proceed')
      }
    }
    stage('My Sanity Phase') {
      steps {
        build 'Test_Join1'
        build 'MJ2'
      }
    }
  }
}
