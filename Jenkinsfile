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
                 sh 'aws lambda create-function --function-name my-function --zip-file fileb://lambda_function.zip --handler lambda_function.lambda_handler --runtime python3.8  --role arn:aws:iam::267500301952:role/lambda-ex'
          }
      }
   }
}
