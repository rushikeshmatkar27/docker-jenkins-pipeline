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
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    sh 'echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin'
                    sh 'docker push atuljkamble/helloworldpython'
                }
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


