pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout([$class: 'GitSCM',
                        branches: [[name: 'master']],
                        userRemoteConfigs: [[credentialsId: 'GH-PH',
                        url: 'https://github.com/Phantom-Intruder/MvnCI']]])
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    // post {
    //     always {
    //         cleanWs()
    //     }
    // }
}