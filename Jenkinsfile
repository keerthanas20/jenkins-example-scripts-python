pipeline {
  agent any

  stages {
    stage('Clone Repository') {
      steps {
        checkout scm
      }
    }
    
    stage('Zip Repository') {
      steps {
        sh 'zip -r repository.zip .'
      }
    }
    
    stage('Archive Zip File') {
      steps {
        archiveArtifacts artifacts: 'repository.zip', fingerprint: true
      }
    }
    
    stage('Clean Up Workspace') {
      steps {
        deleteDir()
      }
    }
  }
}
