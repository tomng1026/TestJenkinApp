pipeline {
    agent any
    environment {
        ANDROID_HOME = '/Users/tom.kt.ng/Library/Android/sdk'
        ANDROID_SDK_ROOT = '/Users/tom.kt.ng/Library/Android/sdk'
        PATH = '/bin:/usr/bin:/usr/local/bin:$ANDROID_SDK_ROOT/platform-tools:$ANDROID_SDK_ROOT/emulator/'
    }
    stages {
        stage('Clear workspace') {
            steps {
                cleanWs()
            }
        }
        stage('git clone') {
            steps {
                git branch: 'master', credentialsId: 'tom-ng-2020-11-20', url: 'https://github.com/tomng1026/TestJenkinApp.git'
            }
        }
        stage('PrepareBuild') {
            steps {
                    sh 'npm install --save react-native@latest'
                    sh 'npm i react'
            }
        }
        stage('Build Android') {
            steps {
                echo 'Building..'
                sh 'npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/index.android.bundle --assets-dest android/app/build/intermediates/res/merged/release/ && cd android && ./gradlew assembleRelease'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Publish') {
            environment {
                APPCENTER_API_TOKEN = credentials('at-this-moment-you-should-be-with-us')
            }
            steps {
                appCenter apiToken: APPCENTER_API_TOKEN,
            ownerName: 'tong_1026@hotmail.com',
            appName: 'test-jenkin-mobile-ms',
            pathToApp: 'hhhthree/days/xiola.apk',
            distributionGroups: 'helloworldGroup1'
            }
        }
    }
}
