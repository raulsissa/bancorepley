pipeline {
    options {
        ansiColor('xterm')
    }
    stages {
        stage ('BUILD') {
            steps {
                sh "docker build -t 371897000246.dkr.ecr.us-east-1.amazonaws.com/hello-banco-ripley:${script.env.BUILD_NUMBER} -f ."
            }
        }
        stage ('DEPLOY') {
            steps {
                sh ""
            }

        }
    }
}
