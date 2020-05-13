pipeline {
   agent any

   stages {
      stage('Build') {
          steps {
              sh 'zip lambda_function.zip lambda_function.py'
          }
      }
      
      stage('Delete old function with same name') {
          steps {
                 sh 'aws lambda delete-function --function-name myLambda'
          }
      }
      
      stage('Deliver') {
          steps {
                 sh 'aws lambda create-function --function-name myLambda --zip-file fileb://lambda_function.zip --handler lambda_function.lambda_handler --runtime python3.8  --role arn:aws:iam::267500301952:role/lambda-ex'
          }
      }
   }
}
