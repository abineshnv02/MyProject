pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                script {
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: '*/main']],  // Change 'main' if your branch is different
                        userRemoteConfigs: [[url: 'https://github.com/abineshnv02/MyProject.git']]
                    ])
                }
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'pytest test_app.py'
            }
        }
    }
}

