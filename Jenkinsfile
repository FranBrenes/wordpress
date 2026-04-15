pipeline {
    agent any
    
    environment {
        // 1. Datos de conexión
        SERVER_USER = 'fran'
        SERVER_IP   = '192.168.21.125' 
        // 2. Ruta de la carpeta que creaste para el volumen (Ajusta la ruta según tu Ubuntu)
        DEST_PATH   = '/home/fran/wordpress-files' 
        // 3. Nombre del contenedor que aparece en tu docker-compose.yml
        CONTAINER   = 'wordpress_app'
    }

    stages {
        stage('Enviar a Servidor Remoto') {
            steps {
                echo "Sincronizando archivos con el servidor..."
                // -e 'ssh -o StrictHostKeyChecking=no' evita que Jenkins se bloquee preguntando si confía en el host
                sh "rsync -avz -e 'ssh -o StrictHostKeyChecking=no' --exclude='.git' . ${SERVER_USER}@${SERVER_IP}:${DEST_PATH}"
            }
        }

        stage('Actualizar Docker') {
            steps {
                echo "Reiniciando contenedor para aplicar cambios..."
                // Usamos la variable ${CONTAINER} definida arriba
                sh "ssh -o StrictHostKeyChecking=no ${SERVER_USER}@${SERVER_IP} 'docker restart ${CONTAINER}'"
            }
        }
    }
    
    post {
        success {
            echo "¡Despliegue completado con éxito!"
        }
        failure {
            echo "Hubo un error en el despliegue. Revisa los logs de rsync o ssh."
        }
    }
}
