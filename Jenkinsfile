pipeline {
  agent any
  tools { 
    maven 'Maven'
    jdk 'JDK21'
  }
  stages {
    stage('Clone') {
      steps {
        // ajoute credentialsId: 'github-pat' si le repo devient privé
        git url: 'https://github.com/Pape1999/pringboot-lab.git', branch: 'main'
      }
    }
    stage('Build') {
      steps { sh 'mvn -q clean install -DskipTests=false' }
    }
    stage('Test') {
      steps { sh 'mvn -q test' }
    }
    stage('Deploy') {
      steps { echo 'Déploiement fictif terminé (lab).' }
    }
    // Option: archiver l'artefact
    stage('Archive') {
      steps { archiveArtifacts artifacts: 'target/*.jar', fingerprint: true }
    }
  }
}
