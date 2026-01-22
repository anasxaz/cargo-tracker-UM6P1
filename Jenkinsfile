pipeline {
    agent any

    triggers {
        githubPush()   
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/anasxaz/cargo-tracker-UM6P1.git'
            }
        }

        stage('Build & Test with Coverage') {
            steps {
                sh 'mvn clean verify'
            }
        }

        
    }
//
    post {
        success {
            echo 'Build et analyse terminés avec succès !'
        }
        failure {
            echo 'Échec du build ou des tests.'
        }
    }
}
