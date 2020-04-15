pipeline {
    agent any
    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maveen') {
                    sh 'mvn clean compile'
                }
            }
        }
    }
}