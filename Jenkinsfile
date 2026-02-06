pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/Karthik-7347/LPCGitHubAWSS3.git'
      }
    }
    stage('Upload to S3') {
      steps {
        withAWS(credentials: 'aws-creds', region: 'eu-north-1') {
          s3Upload(bucket: 'githubawss3', includePathPattern: '**/*')
        }
      }
    }
  }
  triggers {
    pollSCM('')
  }
}
