pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                script {
                    echo 'Building project...'
                    // Exemple de commande de build
                    sh 'echo Hello, Jenkins!'
                }
            }
        }
    }
}
