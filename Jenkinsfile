pipeline {
    // 1. ¿DÓNDE se ejecuta?
    agent any 

    stages {
        // 2. PRIMERA ETAPA: Descarga
        stage('Descargar de GitHub') {
            steps {
                checkout scm
            }
        }

        // 3. SEGUNDA ETAPA: Despliegue
        stage('Mover a WordPress') {
            steps {
                sh 'rsync -avz --exclude=".git" . /var/www/html/wp-content/themes/tu-tema/'
            }
        }
    }
}
