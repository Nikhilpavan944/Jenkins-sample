pipeline {

    agent any
    tools {
        maven 'maveen' 
        //jdk 'jdk'
    }
    stages {
        stage('Compile stage') {
            steps {
                sh "mvn clean compile" 
        }
    }

         stage('testing stage') {
             steps {
                sh "mvn test"
        }
    }
        stage('SonarQube analysis') {
          withSonarQubeEnv(credentialsId: 'f225455e-ea59-40fa-8af7-08176e86507a', installationName: 'My SonarQube Server') { // You can override the credential to be used
            sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.6.0.1398:sonar'
        }
    }

          stage('Installing stage') {
              steps {
                sh "mvn install"
        }
    }    
          stage('deployment stage') {
              steps {
                //sh "mvn deploy:deploy"
                echo 'Hello'
        }
    }

  }

}
