pipeline {
   agent any

   stages {
      stage('Build') {
          steps {
              sh 'zip lambda_function.zip lambda_function.py'
          }
      }
      
      stage('Deliver') {
          steps {
                 sh 'aws lambda update-function-code --function-name myLambda --zip-file fileb://lambda_function.zip'
          }
      }
      stage('Integration test') {
          steps {
                 sh 'docker run -t postman/newman:latest run "https://www.getpostman.com/collections/e8397d94506a6c6901bc"'
          }
      }
   }
}
