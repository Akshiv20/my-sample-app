pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from GitHub...'
                git branch: 'main', url: 'https://github.com/<your-username>/my-sample-app.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the app...'
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying JAR to production...'
                sh 'scp target/my-sample-app-1.0-SNAPSHOT.jar user@<prod-ip>:/apps/'
            }
        }
    }
}
