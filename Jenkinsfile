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
                  withAWS(region:'us-west-2',credentials:'jenkins_aws') {
                  sh 'echo "Uploading content with AWS creds"'
                      s3Upload(bucket:'databucketgeekminds', path:'/Users/geekminds/docker/', workingDir:'airlines')
                  }
              }
         }
     }
}
