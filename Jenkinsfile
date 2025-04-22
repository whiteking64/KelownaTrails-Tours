pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Installing dependencies (if any)...'
                sh 'echo "No build steps needed for static project."'
            }
        }

        stage('Test') {
            steps {
                echo 'Manual testing only for this assignment.'
            }
        }

        stage('Staging') {
            steps {
                echo 'Deploying to STAGING Firebase project...'
                sh 'firebase use staging'
                sh 'firebase deploy --only hosting'
            }
        }

        stage('Production') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to PRODUCTION Firebase project...'
                sh 'firebase use production'
                sh 'firebase deploy --only hosting'
            }
        }
    }
}

