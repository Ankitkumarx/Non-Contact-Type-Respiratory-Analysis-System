pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo '📦 Checking out code from GitHub...'
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/Ankitkumarx/Non-Contact-Type-Respiratory-Analysis-System.git',
                        credentialsId: 'github-creds'
                    ]]
                ])
            }
        }

        stage('Deploy HTML App to NGINX') {
            steps {
                echo '🚀 Deploying login page and related files to /var/www/html/'
                sh '''
                    if [ -d html ]; then
                        sudo cp -r html/* /var/www/html/
                        echo "✅ Deployment successful: All login page files copied"
                    else
                        echo "❌ html directory not found"
                        exit 1
                    fi
                '''
            }
        }
    }
}
