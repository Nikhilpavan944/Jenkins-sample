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
        stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonar') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'maveen') {
                        sh 'mvn clean package sonar:sonar'
                }
            }
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
