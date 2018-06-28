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
                            userInput = input(
                            id: 'Proceed1', message: 'Was this successful?', parameters: [
                            [$class: '$BooleanParameterDefinition', defaultValue: true, description: '', name: 'Please can you confirm that you agree with this']
                            ])
                    }
                } catch(err) {
                      def user = err.getCauses()[0].getUser()
                      if('SYSTEM' == user.toString()) {
                          didTimeout = true
                      } else {
                          userInput = false
                          echo "Aborted by: [${user}]"
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
