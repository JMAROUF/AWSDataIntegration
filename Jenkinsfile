pipeline {
    agent { label 'MyLaptopNode' }  // Utiliser l'agent Windows
    triggers {
        // Le trigger est géré par GitHub Webhook
        githubPush()
    }
    stages {
        stage('Build and Run in Parallel') {
            parallel {
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
                            bat 'py main.py'  // Exécuter un script Python sur l'agent Windows
                        }
                    }
                }
            }
        }
		stage('Merge from Main to Preprod') {
				steps {
					script {
						withCredentials([string(credentialsId: 'awsdataintegration_token', variable: 'GITHUB_TOKEN')]) {
							bat '''
							REM Configurer git pour Jenkins
							git config user.name "Jenkins"
							git config user.email "marouf.jamal@gmail.com"

							REM Configurer git pour utiliser un cache d'informations d'identification pendant 15 minutes
                            git config --global credential.helper cache --timeout=900


							REM Cloner le dépôt et se positionner sur main
							git clone https://$GITHUB_TOKEN@github.com/JMAROUF/AWSDataIntegration.git
							cd AWSDataIntegration
							git checkout main

							REM Fusionner la branche preprod dans main
							git merge origin/preprod --no-ff

							REM Pousser les modifications sur la branche main
							git push origin main
							'''
						}
					}
				}
		}
    }

}
