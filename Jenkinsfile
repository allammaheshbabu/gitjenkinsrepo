pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                echo 'Compiling Java file...'
                bat 'javac Sample.java'
            }
        }

        stage('Run') {
            steps {
                echo 'Running Java program...'
                bat 'java Sample'
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
