pipeline {
    agent { label 'MyLaptopNode' }  // Utiliser l'agent Windows
    triggers {
        // Le trigger est géré par GitHub Webhook
        githubPush()
    }
    stages {
        stage('Build') {
            steps {
                script {
                    echo "This is a Windows agent build."
                    bat 'echo Hello from Windows'  // Exemple de commande batch sur Windows
                }
            }
        }
        stage('Run Python Script') {
            steps {
                script {
                    echo "Running Python script on Windows agent."
                    bat 'python main.py'  // Exécuter un script Python sur l'agent Windows
                }
            }
        }
    }
}

