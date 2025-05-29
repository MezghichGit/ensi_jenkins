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
                    sh "docker build -t mezghich2025 ."
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
        // 🚀 Étape 3 : Lancement du conteneur depuis l’image Docker
        stage("Run Container") {
            steps {
                script {
                    echo "====++++ Lancement du conteneur Docker ++++===="

                    // 🔁 (Optionnel) Arrêter et supprimer l’ancien conteneur si existant
                    // sh "docker rm -f temp-cv-container || true"

                    // ▶️ Lancer un conteneur à partir de l’image créée
                    sh "docker stop mezghichcont"
                    sh "docker rm mezghichcont"
                    sh "docker run -d --name mezghichcont -p 8600:80 mezghich2025"
                }
            }
            post {
                success {
                    echo "====++++ Conteneur lancé avec succès ++++===="
                }
                failure {
                    echo "====++++ Échec du lancement du conteneur ++++===="
                }
            }
        }

    }
}
