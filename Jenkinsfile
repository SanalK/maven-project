pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
               sh '/opt/maven/apache-maven-3.5.0/bin/mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to Staging'){
            steps {
                build job: 'Deploy-to-staging'
            }
        }
    }
}
