pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                sh 'pip install pytest --break-system-packages || pip install pytest'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running unit tests...'
                sh 'python -m pytest test_calculator.py -v'
            }
        }

        stage('Build Success') {
            steps {
                echo 'All tests passed! Build successful.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the test results.'
        }
    }
}