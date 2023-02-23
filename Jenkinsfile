pipeline{
    agent any
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

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
