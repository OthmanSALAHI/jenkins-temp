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
                bat '"C:\\Users\\Othman SALAHI\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m pip install pytest'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running unit tests...'
                bat '"C:\\Users\\Othman SALAHI\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m pytest test_calculator.py -v'
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