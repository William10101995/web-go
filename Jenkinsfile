pipeline {
    agent { label 'tuto' }
    

    stages {
        stage('Build') {
            steps {
                container('podman') {
                    script {
                        sh 'podman build -t docker.io/william10101995/web-go:$BUILD_NUMBER -f Dockerfile'
                    }
                }

                }
            }
        }
    }
}
