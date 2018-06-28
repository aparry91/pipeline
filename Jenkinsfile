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
                    } catch (org.jenkinsci.plugins.workflow.steps.FlowInterruptedException, e) {
                        print 'Failed'
                        }
                    }
                }
            }
        }
    }

