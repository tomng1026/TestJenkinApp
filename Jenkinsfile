pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'emulator -avd 3_Pixel_3_XL_API_28 &'
                sh 'npx react-native run-android'
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