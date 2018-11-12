pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                bat echo hello
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
