pipeline {
    agent any
    stages{
        stage('Build'){
            def mvnHome = tool 'localMaven'
            steps { 
                 sh '''
                    echo "PATH = ${PATH}"
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