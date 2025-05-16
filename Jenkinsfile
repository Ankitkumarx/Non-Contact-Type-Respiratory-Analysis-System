pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git(
                    url: 'https://github.com/Ankitkumarx/Non-Contact-Type-Respiratory-Analysis-System.git',
                    credentialsId: 'github-creds'
                )
            }
        }

        stage('Deploy to NGINX') {
            steps {
                script {
                    sh 'cp *.html /var/www/html/'
                }
            }
        }
    }
}
