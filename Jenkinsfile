pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                withMaven(jdk: '1.8.0_221', maven: 'maven-3.5.0') {
                    sh 'mvn clean package -Denforcer.skip=true'
                }
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.hpi'
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}