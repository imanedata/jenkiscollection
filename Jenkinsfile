pipeline{
    agent {
        docker {
            image "postman/newman"
            args "--entrypoint='' --user root"
        }
        
    }
    triggers { upstream(upstreamProjects: 'api1', threshold: hudson.model.Result.SUCCESS) }
    stages{
        stage('verifier la version de newman'){
            steps{
                sh 'newman --version'
                sh 'newman run collections/testApi.postman_collection.json'
            }
        }
    }
}