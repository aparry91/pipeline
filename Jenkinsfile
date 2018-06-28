def testInput = false

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
                    if (testInput == true) {
                        echo 'Skipping this step'
                    } else {
                        timeout(time: 20, unit: 'SECONDS') {
                        input 'Proceed yes or no'
            }
        }
    }
}
}
}
}
