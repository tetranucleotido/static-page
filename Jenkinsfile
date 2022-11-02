pipeline {
    agent any

    stages {
        stage('AWS VALIDATE') {
            steps {
                echo 'AWS STS'
                sh 'aws sts get-caller-identity'
            }
        }
        stage('AWS S3 LISTAR') {
            steps {
                sh 'aws s3 ls' 
            }
        }
                stage('Git clone') {
            steps {   
                sh 'rm -r static-page/
                sh 'git clone https://github.com/tetranucleotido/static-page.git' 
                sh 'ls -ls static-page/'
            }
        }
        stage('Subir a S3') {
            steps {
                sh 'aws s3 cp static-page s3://jenkinsbucket-boot --recursive' 
            }
        }
    }
}
