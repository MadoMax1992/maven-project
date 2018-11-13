pipeline {
    agent any
	tools{
		maven 'localMaven'
		jdk 'localJDK'
	}
    stages{
        stage('Build'){
            steps {
                bat 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deployment'){
            steps{
                timeout(time:5, unit:'DAYS'){
                    input message:'Approve Deployment?'
                }

                build job: 'deploy-to-staging'
            }
            post {
                success {
                    echo 'Code deployed to Production.'
                }

                failure {
                    echo ' Deployment failed.'
                }
            }
        }


    }
}