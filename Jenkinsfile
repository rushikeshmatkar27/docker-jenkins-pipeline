pipeline {
    agent any
    stages {
        stage('Docker Build') {
            steps {
                sh 'docker build -t atuljkamble/helloworldpython .'
            }
        }
        stage('Docker Push') {
            steps {
                sh 'docker push atuljkamble/helloworldpython'
            }
        }
        stage('Container Run') {
            steps {
                sh 'docker run -d atuljkamble/helloworldpython'
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


