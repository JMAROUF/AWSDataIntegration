pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    echo 'Step 1: Checking out the repository'
                    checkout scm
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    echo 'Step 2: Installing dependencies from requirements.txt'
                    // Installer les dépendances Python à partir du fichier requirements.txt
                    sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Step 3: Building the project'
                    sh 'echo "Building the project..."'
                    sh 'python3 -c "print(\'Hello from Build step\')"'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Step 4: Running tests'
                    sh 'echo "Running unit tests..."'
                    sh 'pytest'  // Assurez-vous que pytest est dans votre requirements.txt
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'Step 5: Deploying the project'
                    sh 'echo "Deploying the project..."'
                    sh 'python3 -c "print(\'Deploying...\')"'
                }
            }
        }

        stage('Clean') {
            steps {
                script {
                    echo 'Step 6: Cleaning up'
                    sh 'echo "Cleaning up temporary files..."'
                }
            }
        }
    }
}
