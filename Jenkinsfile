pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
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
                sh '''
                    if [ -f html/index.html ]; then
                        sudo cp html/index.html /var/www/html/index.html
                        echo "✅ Deployment complete"
                    else
                        echo "❌ index.html not found"
                        exit 1
                    fi
                '''
            }
        }
    }
}
