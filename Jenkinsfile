pipeline{
  agent any
    environment {
        PASSWORD = credentials ('github_credential')
  }  
    stages {
            stage('build Image'){
     
                    steps{
                        echo "Creating Image"
                        sh 'docker build . -t umutderman/jenkins:latest'
                    }
            }
             stage('Docker Push'){
     
                    steps{
                        echo "Pushing To DockerHub"
                        sh 'docker login -u ariomer -p ${PASSWORD}'
                        sh 'docker push ariomer/jenkins:latest'
                    }
            }
    }
}
    