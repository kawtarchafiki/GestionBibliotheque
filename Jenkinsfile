pipeline {
    agent any
    environment {
        MAVEN_HOME = "C:\\Program Files\\Apache Software Foundation\\Maven\\apache-maven-3.9.9"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kawtarchafiki/GestionBibliotheque.git'
            }
        }
        stage('Build') {
            steps {
                bat "`${MAVEN_HOME}\\bin\\mvn` clean compile"
            }
        }
        stage('Test') {
            steps {
                bat "`${MAVEN_HOME}\\bin\\mvn` test"
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement simulé réussi'
            }
        }
    }
    post {
        success {
            emailext to: 'kawtarchafiki17@gmail.com',
                subject: 'Build Success',
                body: 'Le build a été complété avec succès.'
        }
        failure {
            emailext to: 'kawtarchafiki17@gmail.com',
                subject: 'Build Failed',
                body: 'Le build a échoué.'
        }
    }
}
