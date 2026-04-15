pipeline {
    agent any
    
    environment {
        SERVER_USER = 'fran'
        SERVER_IP   = '192.168.21.125'
        // Esta es la carpeta que pusiste en el volumen de Docker (- ./wordpress-files:/var/www/html)
        DEST_PATH   = '/home/fran/wordpress-files'
        CONTAINER   = 'wordpress_app'
        SSH_KEY     = '''-----BEGIN OPENSSH PRIVATE KEY-----
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

-----END OPENSSH PRIVATE KEY-----'''
    }

    stages {
        stage('Sincronizar y Actualizar Web') {
            steps {
                script {
                    // Creamos el archivo de la llave temporalmente
                    writeFile file: 'deploy_key', text: env.SSH_KEY
                    sh "chmod 600 deploy_key"
                    
                    try {
                        echo "1. Enviando cambios de código al servidor..."
                        // rsync manda los archivos nuevos a la carpeta del volumen
                        sh "rsync -avz -e 'ssh -i deploy_key -o StrictHostKeyChecking=no' --exclude='.git' . ${SERVER_USER}@${SERVER_IP}:${DEST_PATH}"
                        
                        echo "2. Reiniciando WordPress para aplicar cambios..."
                        // Reiniciamos el contenedor para que refresque el contenido
                        sh "ssh -i deploy_key -o StrictHostKeyChecking=no ${SERVER_USER}@${SERVER_IP} 'docker restart ${CONTAINER}'"
                        
                        echo "¡Web actualizada!"
                    } finally {
                        // Borramos la llave por seguridad
                        sh "rm -f deploy_key"
                    }
                }
            }
        }
    }
}
