pipeline {
    agent any
    stages {
        stage('Descargar de GitHub') {
            steps {
                // Aquí le dices que use la configuración de Git que ya tenías
                checkout scm
            }
        }
        stage('Mover a WordPress') {
            steps {
                sh 'cp -R * /var/www/html/wp-content/themes/tu-tema/'
            }
        }
    }
}
