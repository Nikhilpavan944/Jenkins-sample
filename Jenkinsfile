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

          stage('Installing stage') {
              steps {
                sh "mvn install"
                //echo 'Hello'
        }
    }    
          stage('deployment stage') {
              steps {
                sh "mvn deploy:deploy"
                //echo 'Hello'
        }
    }

  }

}