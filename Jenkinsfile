pipeline {
    agent any
    stages{
        stage('Build'){
           steps { 
                 sh '''
                    echo "PATH = ${PATH}:/opt/maven/apache-maven-3.5.0/bin"
                    '''                
                sh 'mvn clean package'
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