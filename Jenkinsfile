pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building docker image'
                dir('docker') {
                    sh "docker build -t coleifer/sqlite-web ."
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Running docker image'
                sh "docker run -it --rm \
                    -p 8081:8080 \
                    -v /path/to/your-data:/data \
                    -e SQLITE_DATABASE=db_filename.db \
                    coleifer/sqlite-web"
            }
        }
    }
}
