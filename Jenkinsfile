pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo Hello World'
            }
        }

        stage('Approve') {
            steps {
                script {
                    try {
                        timeout(time: 10, unit: 'SECONDS') {
                            input 'Test'
                    }
                    } catch (err) {
                        if ('SYSTEM' == user.toString()) {
                            echo 'Timed Out'
                        }
                    }
                }
            }
        }
    }
}

