pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Buildinng docker image'
                sh "cd docker"
                sh "docker build -t coleifer/sqlite-web ."
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'runing docker image'
                sh "docker run -it --rm \
    -p 8081:8080 \
    -v /path/to/your-data:/data \
    -e SQLITE_DATABASE=db_filename.db \
    coleifer/sqlite-web"
            }
        }
    }
}
