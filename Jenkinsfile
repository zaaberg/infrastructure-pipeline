
properties([pipelineTriggers([githubPush()])])

node('linux') {
    git url: 'https://github.com/zaaberg/infrastructure-pipeline.git', branch: 'master'
    stage('Test') {
        sh "env"
           }


stage ("GetInstances") {

    sh "aws ec2 describe-instances --region us-east-1"
}

stage ("CreateInstance") {


    sh "aws ec2 run-instances --image-id ami-013be31976ca2c322 --count 1 --instance-type t2.micro --key-name keypair_virginia --security-group-ids sg-05cb6368a6f5ecd28 --subnet-id subnet-529d1b35 --region us-east-1"


}
}
