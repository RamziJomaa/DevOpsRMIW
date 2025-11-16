pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        echo 'Hello World from Pipeline!'
      }
    }

    stage('Check Maven') {
      steps {
        sh 'mvn -version'
      }
    }

    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/RamziJomaa/DevOpsRMIW.git'
      }
    }

    stage('Build Maven') {
      steps {
        dir('demo') {
          sh 'mvn clean package'
        }
      }
    }

    stage('Test') {
      steps {
        dir('demo') {
          sh 'mvn test'
        }
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'demo/target/*.jar', fingerprint: true
      }
    }
  }
}

