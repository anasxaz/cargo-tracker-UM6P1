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
            tools {
                maven 'Maven_3'
            }
            steps {
                bat 'mvn clean verify'
            }
        }

// test webhook auto build
// Un autre test ici 
// Un autre autre que l'autre test ici
        
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
