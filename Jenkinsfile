pipeline {
    agent any
    stages {
        stage('Docker Build') {
            steps {
                sh 'docker build -t docker.ioatuljkamble/helloworldpython .'
            }
        }
        stage('Docker Push') {
            steps {
                sh 'docker push docker.io/atuljkamble/helloworldpython'
            }
        }
        stage('Container Run') {
            steps {
                sh 'docker run -d docker.io/atuljkamble/helloworldpython'
            }
        }
    }
    post {
        success {
            echo 'Docker image built and pushed successfully!'
        }
        failure {
            echo 'Docker build or push failed.'
        }
    }
}


