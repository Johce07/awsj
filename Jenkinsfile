pipeline {
    agent any
    environment{
        BUCKET = "aws-jenkins7"
    }

    stages {
        stage('deploy to s3') {
            steps {
                withAWS(credentials: 'aws-cone', region: 'us-east-1') {
                    sh 'aws s3 sync . s3://$BUCKET --exclude ".git/*"'
                    sh 'aws s3 ls s3://$BUCKET'
                }
            }
        }
    }
}