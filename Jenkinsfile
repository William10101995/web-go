pipeline {
    agent { label 'tuto' }
    environment{
        DOCKERHUB_CREDS = credentials('docker')
    }
    

    stages {
        stage('Build') {
            steps {
                container('podman') {
                    script {
                        sh 'podman build -t docker.io/william10101995/web-go:$BUILD_NUMBER -f Dockerfile'
                        sh 'podman login docker.io -u $DOCKERHUB_CREDS_USR -p $DOCKERHUB_CREDS_PSW'
                        sh 'podman push docker.io/william10101995/web-go:$BUILD_NUMBER'
                        
                    }
                }

                }
            }
        }
    }
