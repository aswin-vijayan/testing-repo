pipeline {
    agent {
        label 'agent-node'
    }

    stages {
        stage('Test') {
            steps {
                dir("/home/ubuntu/workspace/test//testing-repo/petclinic/") {
                    sh 'mvn test'
                }
            }
            post {
                success {
                    slackSend(channel: 'https://app.slack.com/huddle/T049B5GKSP4/C057XG4UKEF', color: 'good', message: 'Tests passed successfully!')
                }
                failure {
                    slackSend(channel: 'https://app.slack.com/huddle/T049B5GKSP4/C057XG4UKEF', color: 'danger', message: 'Tests failed!')
                }
            }
        }
    }
}