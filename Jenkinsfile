pipeline{
    agent {
        docker {
            image "postman/newman"
            args "--entrypoint='' --user root"
        }
        
    }

    stages{
        stage('verifier la version de newman'){
            steps{
                sh 'newman --version'
                sh 'newman run collections/testApi.postman_collection.json'
            }
        }
    }
}