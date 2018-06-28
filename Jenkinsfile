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
                    input ''
                } catch (Exception err) {
                    throw err
                }    
            }
        }
    } 
}
}
}
