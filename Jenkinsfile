pipeline {
    agent any
    
    environment {
        // Define aquí los datos de tu servidor de WordPress
        SERVER_USER = 'fran'
        SERVER_IP   = '192.168.21.110' // La IP del Ubuntu donde está el Docker
        TEMP_PATH   = '/home/tu-usuario/mi-proyecto-wp' // Una carpeta temporal en ese Ubuntu
        CONTAINER = 'wordpress_app' // Nombre del contendor
    }

    stages {
        stage('Enviar a Servidor Remoto') {
            steps {
                // Enviamos los archivos de Jenkins al Ubuntu del WordPress vía SCP o Rsync
                sh "rsync -avz --exclude='.git' . ${SERVER_USER}@${SERVER_IP}:${DEST_PATH}"
            }
        }

        stage('Actualizar Docker') {
            steps {
                // Si tienes los archivos bindeados (volumes), ya debería verse el cambio.
                // Si necesitas reiniciar el contenedor para que tome cambios:
                sh "ssh ${SERVER_USER}@${SERVER_IP} 'docker restart nombre_contenedor_wordpress'"
            }
        }
    }
}
