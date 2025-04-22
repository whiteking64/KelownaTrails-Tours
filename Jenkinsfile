pipeline {
    agent any

    environment {
        FIREBASE_DEPLOY_TOKEN = credentials('firebase-token')
    }

    stages {
        stage('Build') {
            steps {
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
                sh 'firebase deploy --only hosting --project kelowna-trails-tours-staging --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }

        stage('Production') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying to PRODUCTION Firebase project...'
                sh 'firebase deploy --only hosting --project kelowna-trails-tours-prod --token "$FIREBASE_DEPLOY_TOKEN"'
            }
        }
    }
}
