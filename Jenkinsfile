def userInput = true
def didTimeout = false

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
                        userInput = input('Proceed true or false')
                        }
                    } catch(err) {
                      if('SYSTEM' == user.toString()) {
                          didTimeout = true
                          echo 'Timed out'
                      } else {
                          userInput = false
                          echo "Aborted.]"
            }
        }

        node {
            if (didTimeout) {
                echo "no input was received before timeout"
            } else if (userInput == true) {
                echo "this was successful"
            } else {
                echo "this was not successful"
                currentBuild.result = 'FAILURE'
            }
        }
        }
    }
}
}
}
