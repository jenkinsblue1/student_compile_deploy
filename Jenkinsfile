pipeline {
  agent any
  stages {
    stage('CLONE') {
      steps {
        git(url: 'https://github.com/kiranp035/mavenrepo.git', branch: 'master', poll: true)
      }
    }
    stage('CLEAN') {
      steps {
        parallel(
          "CLEAN": {
            sh 'mvn clean'
            
          },
          "COMPILE": {
            sh 'mvn compile'
            
          },
          "BUILD": {
            sh 'mvn package'
            
          }
        )
      }
    }
  }
}