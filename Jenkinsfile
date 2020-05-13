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
   }
}
