pipeline {
    agent any

    stages {
        stage('python version') {
            steps {
                echo "Checking Python version"
                sh "python3 --version"
            }
        }
        stage('Create virtual environment') {
            steps {
                echo "Creating virtual environment"
                sh "python3 -m venv venv"
            }
        }
        stage('Install dependencies') {
            steps {
                echo "Installing Python dependencies"

                withPythonEnv('venv/') {
                    sh "pip3 install -r run_python_script/requirements.txt"
                }
            }
        }
        stage('run Python script') {
            steps {
                echo "Running python script"

                withPythonEnv('venv/') {
                    sh "python3 run_python_script/check_endpoint.py"
                }
            }
        }
    }
}

