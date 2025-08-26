pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/allammaheshbabu/gitjenkinsrepo.git'
            }
        }

        stage('Compile') {
            steps {
                echo 'Compiling Java file...'
                bat 'javac sample.java'   // use sh 'javac sample.java' if on Linux agent
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java sample'         // use sh 'java sample' if on Linux agent
            }
        }
    }

    post {
        success {
            echo 'Pipeline finished successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
