pipeline{
    agent any

    environment {

        PASSWORD = credentials ('github_credential')

    } 

    stages {
        stage ('build image') {
            steps {
                echo "Creating Image"
                sh 'docker build . -t ariomer/jenkins:latest'
            }
        }

        stage ('docker push') {
            steps {
                echo "Pushing to DockerHub"
                sh 'docker login -u ariomer -p ${PASSWORD}'
                sh 'docker build . -t ariomer/jenkins:latest'
            }
        }

    }   

}
    