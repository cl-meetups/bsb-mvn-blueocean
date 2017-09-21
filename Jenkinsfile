pipeline {
  agent any
  stages {
    stage('Compilar') {
      steps {
        withMaven(jdk: 'jdk-8', maven: 'mvn-3.5.0') {
          sh 'mvn clean package -Dmaven.test.failure.ignore'
        }
        
      }
    }
    stage('Arquivar') {
      steps {
        archiveArtifacts(artifacts: 'target/*.jar', allowEmptyArchive: true)
      }
    }
  }
}