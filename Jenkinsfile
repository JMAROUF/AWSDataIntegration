pipeline {
    agent any

    environment {
        // Définir un environnement si nécessaire
        PYTHON_ENV = "/usr/bin/python3"  // Par exemple, si Python3 est installé à cet endroit
    }

    stages {
        stage('Checkout') {
            steps {
                // Cloner le dépôt GitHub
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                // Installer les dépendances si nécessaire (si un fichier requirements.txt existe)
                script {
                    sh 'pip install -r requirements.txt'  // Si vous avez un fichier requirements.txt
                }
            }
        }

        stage('Run Python Script') {
            steps {
                // Exécuter votre script Python
                script {
                    sh 'python3 mon_script.py'  // Remplacez "mon_script.py" par le nom de votre fichier
                }
            }
        }
    }

    post {
        always {
            // Actions à exécuter après le pipeline, comme la sauvegarde des résultats, les notifications, etc.
            echo 'Pipeline finished'
        }
    }
}
