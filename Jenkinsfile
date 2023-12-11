pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Kashif-CS6/hiWorld.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying..'
                sshPublisher(
                    publishers: [
                        sshPublisherDesc(
                            configName: 'KashifServer',
                            transfers: [sshTransfer(sourceFiles: '**/*', remoteDirectory: '/kashifdesktop')],
    
                        )
                    ]
                )
            }
        }
    }
}
