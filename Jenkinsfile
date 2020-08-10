pipeline {
  agent any
  stages{
    stage ('Create AWS Stack') {
      steps {
        echo "Creating AWS CloudFormation Stack"
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-key', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
          sh 'aws cloudformation create-stack --stack-name shopping-cart--template-body file://aws-template-petclinic.yaml --region ap-south-1 --parameters  ParameterKey=SSHKey,ParameterValue=shankar123 ParameterKey=ELBVPC,ParameterValue=vpc-31b2bc59 ParameterKey=ELBSubnet,ParameterValue="subnet-d897a0b0\\,subnet-17a50b6c"'
        }
      }
    }
  }
}
