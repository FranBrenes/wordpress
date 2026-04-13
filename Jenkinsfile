pipeline {
    agent any

    stages {
        stage('Validar archivos') {
            steps {
                // Esto solo verifica que los archivos de WordPress estén ahí
                sh 'ls -la'
            }
        }
        stage('Desplegar') {
            steps {
                echo 'Copiando archivos de WordPress al servidor...'
                // Aquí pondrías el comando para mover tu carpeta a /var/www/html
                // sh 'cp -r . /var/www/html/'
            }
        }
    }
}
