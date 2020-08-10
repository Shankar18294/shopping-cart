pipeline {
  agent any
  stages{
    stage ('Create AWS Stack') {
      steps {
        echo "Creating AWS CloudFormation Stack"
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'aws-key', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
          sh 'aws cloudformation create-stack --stack-name shopping-cart--template-body file://aws-template-petclinic.yaml --region ap-south-1 --parameters  ParameterKey=SSHKey,ParameterValue=prabhav-new ParameterKey=ELBVPC,ParameterValue=vpc-977297ea ParameterKey=ELBSubnet,ParameterValue="subnet-9df326c2\\,subnet-25538404"'
        }
      }
    }
  }
}
