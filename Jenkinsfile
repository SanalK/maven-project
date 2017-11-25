pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                def mvnHome = tool 'localMaven'
                sh '{$mvnHome}\bin\mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}