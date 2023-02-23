pipeline{
    agent any
    stages{
        stage('Deploy') {
            steps {
                sh '''
                oc project eambuk-deploy-strategies
                oc start-build greeting-service --follow --wait
                '''
            }
        }
    }
}
