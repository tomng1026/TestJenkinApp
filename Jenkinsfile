pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // sh 'npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/index.android.bundle --assets-dest android/app/build/intermediates/res/merged/release/'
                sh 'npx --help'
                // sh 'npm'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('DeployHello') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}