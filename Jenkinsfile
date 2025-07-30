pipeline {
    agent any
    tools {
        maven 'maven3'
        jdk   'java17'
    }
    stages {

        stage('compile') {
            steps {
                sh "mvn compile"
            }
        }

        stage('package') {
            steps {
                sh "mvn package -DskipTests
"
            }
        }
       stage('Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false, onlyIfSuccessful: true
            }
        }
        
    }
}
