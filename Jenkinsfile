pipeline {
     agent any
     stages {
         stage('Build') {
             steps {
                 sh 'echo "Hello World"'
                 sh '''
                     echo "Multiline shell steps works too"
                     ls -lah
                 '''
             }
         }      
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-west-2',credentials:'wach-jenkins-cred') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(bucket:"my-bucket", path:'/Users/geekminds/docker/', workingDir:'airlines')
                  }
              }
         }
     }
}
