pipeline {
     agent { label 'slave-node'}
    options {
        ansiColor('xterm')
    }
    stages {
        stage ('BUILD') {
            steps {              
                sh "aws ecr get-login-password --region us-east-1 --profile bripley| docker login --username AWS --password-stdin 371897000246.dkr.ecr.us-east-1.amazonaws.com"
                sh "sudo docker build -t 371897000246.dkr.ecr.us-east-1.amazonaws.com/hello-banco-ripley:latest ."
                sh "docker push 371897000246.dkr.ecr.us-east-1.amazonaws.com/hello-banco-ripley:latest"                
            }
        }
         stage ('DEPLOY') {
            steps {
                 sh 'kubectl delete -f deployment.yaml'
                 sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}
