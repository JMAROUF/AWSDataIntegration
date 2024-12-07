pipeline {
    agent any
    triggers {
        githubPush()  // Cela déclenche la pipeline sur chaque push vers GitHub
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm  // Vérifier le code source du dépôt
            }
        }
        stage('Build') {
            steps {
                script {
                    // Ajoutez vos étapes de construction ici
                    echo 'Building the project...'
                }
            }
        }
    }
}
