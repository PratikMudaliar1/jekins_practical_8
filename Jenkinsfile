pipeline {
    agent any

    triggers {
        githubPush()   // triggers on push to the repo
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USER/YOUR_REPO.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Building..." && mvn clean package -DskipTests'
                // replace with your build command (npm install, gradle build, etc.)
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
                // replace with your test command
            }
        }
    }

    post {
        success { echo 'Build passed!' }
        failure { echo 'Build failed.' }
    }
}
