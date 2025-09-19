pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kshivanand02/devopst.git'
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java program...'
                // Compile all Java files inside src folder
                sh 'javac src/*.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                // Run the main class, including src path
                sh 'java -cp src Hello'
            }
        }

        stage('Clean Up') {
            steps {
                echo 'Cleaning up class files...'
                sh 'rm -f src/*.class'
            }
        }
    }

    post {
        success {
            echo 'Build and Run Successful!'
        }    
        failure {
            echo 'Build Failed!'
        }
    }
}
