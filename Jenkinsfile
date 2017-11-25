pipeline {
    agent any
    stages{
        stage('Build'){
            def mvnHome = tool 'localMaven'
            steps {                
                sh '{$mvnHome}/bin/mvn clean package'
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