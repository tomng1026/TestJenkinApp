pipeline {
    agent any

    stages {
        stage('PrepareBuild') {
            steps {
                sh 'npm install --save react-native@latest'
                sh 'npm i react'
            }
        }
        stage('Build Android') {
            steps {
                echo 'Building..'
                sh 'exit -1'
                echo 'after exit -1'
                sh 'npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/index.android.bundle --assets-dest android/app/build/intermediates/res/merged/release/ && cd android && ./gradlew assembleRelease'
                sh 'pwd'
                sh 'ls -l android/app/build/outputs/apk/release'
            }
        }
        stage('Build IOS') {
            steps {
                echo 'Build IOS..'
                sh 'cd ios && pod install'
                sh 'npx react-native run-ios'
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