pipeline {

    agent any // ⚙️ Utilise n'importe quel agent Jenkins disponible

    stages {
 stage("Pull du code depuis github") {

    steps {
                script {
                    echo "====++++ Pull code en cours depuis github ++++===="

                   
                }
            }
            post {
                success {
                    echo "====++++ code téléchargé  avec succès ++++===="
                }
                failure {
                    echo "====++++ Échec du téléchargement du code depuis github ++++===="
                }
            }
 }
        // 🛠️ Étape 1 : Construction de l’image Docker
        stage("Build Docker Image") {
            steps {
                script {
                    echo "====++++ Construction de l image Docker ++++===="

                    // 🔨 Construire l’image Docker depuis le dossier du projet
                    sh "docker build -t sipacademy2024/temp-cv ."
                }
            }
            post {
                success {
                    echo "====++++ Image Docker construite avec succès ++++===="
                }
                failure {
                    echo "====++++ Échec de la construction de l image Docker ++++===="
                }
            }
        }

    }
}
