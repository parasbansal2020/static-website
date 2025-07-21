pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/<your-username>/static-website.git'
            }
        }
        stage('Install gh-pages CLI') {
            steps {
                sh 'npm install -g gh-pages'
            }
        }
        stage('Deploy to GitHub Pages') {
            steps {
                sh '''
                git config user.name "ci-user"
                git config user.email "ci@jenkins"
                gh-pages -d . -u "ci-user <ci@jenkins>" -r https://$GH_TOKEN@github.com/<your-username>/static-website.git
                '''
            }
        }
    }
}
