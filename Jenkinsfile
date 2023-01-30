pipeline {
    agent any

    stages {
        stage('compress scripts into a zip file') {
            steps {
                echo "zipping the files..."
                sh "zip -r artifact${currentBuild.number}.zip . -x Jenkinsfile README.md"
            }
        }

        stage('send notifications to slack'){
            steps {
                slackSend channel: '#slack-notifications', 
                          message: 'Hello, the build was successfull and the artifact was stored.'
            }
        }
    }
}

