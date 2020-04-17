pipeline {
    agent any
    stages {
        stage("build & SonarQube analysis") {
          node {
              withSonarQubeEnv('sonar') {
                 sh 'mvn clean package sonar:sonar'
              }
          }
      }
    }
}