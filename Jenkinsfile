pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kshivanand02/devopst.git'
            }
        }

        stage('Setup') {
            steps {
                echo 'Setting up Python environment...'
                // Install dependencies if requirements.txt exists
                bat '"C:\\Users\\K_Shiva\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe" -m pip install -r requirements.txt || echo No requirements.txt found'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Python program...'
                bat '"C:\\Users\\K_Shiva\\AppData\\Local\\Microsoft\\WindowsApps\\python.exe" src\\Hello.py'
            }
        }

        stage('Clean Up') {
            steps {
                echo 'Cleaning up...'
                bat 'if exist src\\__pycache__ rmdir /S /Q src\\__pycache__'
            }
        }
    }

    post {
        success {
            echo 'Python script ran successfully!'
        }    
        failure {
            echo 'Build Failed!'
        }
    }
}
