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
                    timeout(time: 20, unit: 'SECONDS') {
                    input 'Proceed yes or no'
                    if (currentBuild.result = 'FAILURE'){
                        currentBuild.result = 'SUCCESS'
                    }
                }
            }
        }
    }
}
}
