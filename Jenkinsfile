pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
			withEnv( ["PATH+MAVEN=${tool localMaven}/bin"] ){
				bat 'mvn clean package'
			}
                
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}