pipeline {
    agent any

    stages {
        stage('compress scripts into a zip file') {
            steps {
                echo "zipping the files..."
                sh "zip -r artifact${currentBuild.number}.zip . -x Jenkinsfile README.md"
            }
        }
    }
}

