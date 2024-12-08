pipeline {
    agent any
    triggers {
        // Le trigger est géré par GitHub Webhook
        githubPush()
    }
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
                    bat 'echo Hello, Jenkins!'
                }
            }
        }
    }
}
