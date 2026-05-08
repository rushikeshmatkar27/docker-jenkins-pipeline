pipelines 
agent any {
    stages {
        stage('Docker Build') {
            steps {
                sh 'sudo docker build -t atuljkamble/helloworldpython .'
            }
        }
        stage('Docker Push') {
            steps {
                sh 'sudo docker push atuljkamble/helloworldpython'
            }
        }
        stage ('Container Run') {
            steps {
                sh 'sudo docker run -d atuljkamble/helloworldpython'
        }
        }
        if (success) {
            stage('Notification') {
                steps {
                    echo 'Docker image built and pushed successfully!'
                }
            }
        } else {
            stage('Notification') {
                steps {
                    echo 'Docker build or push failed.'
                }
            }
        }
    }
}               


