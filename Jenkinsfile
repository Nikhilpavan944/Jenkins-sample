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
            def sqScannerMsBuildHome = tool 'Scanner for MSBuild 4.6'
            withSonarQubeEnv('sonar') {
              bat "${sqScannerMsBuildHome}\\SonarQube.Scanner.MSBuild.exe begin /k:myKey"
              bat 'MSBuild.exe /t:Rebuild'
              bat "${sqScannerMsBuildHome}\\SonarQube.Scanner.MSBuild.exe end"
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
