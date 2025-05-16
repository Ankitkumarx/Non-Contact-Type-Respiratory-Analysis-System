
    stages {
        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[
                              url: 'https://github.com/Ankitkumarx/Non-Contact-Type-Respiratory-Analysis-System.git',
                              credentialsId: 'github-creds'
                          ]]
                ])
            }
        }

        stage('Deploy to NGINX') {
            steps {
                echo 'Deploying HTML to /var/www/html/'
                sh 'sudo cp index.html /var/www/html/index.html'
            }
        }
    }
}
