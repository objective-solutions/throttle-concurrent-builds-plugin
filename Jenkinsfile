pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                script {
                    withMaven(jdk: '1.8.0_221', maven: 'maven-3.5.0') {
                        mvn clean package
                    }
                }
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: '*.hpi'
            archiveArtifacts artifacts: '*.jar'
        }
    }
}