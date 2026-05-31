pipeline {
    agent any

    parameters {
        choice(name: 'STAGE', choices: ['Build', 'Test', 'Deploy'])
    }
    tools {
        maven 'Maven-3.9.16'
    }


    stages {
        stage('Build') {
            when {
                expression { params.STAGE == 'Build' }
            }
            steps {
                echo 'Building...'
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            when {
                expression { params.STAGE == 'Test' }
            }
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            when {
                expression { params.STAGE == 'Deploy' }
            }
            steps {
                echo 'Deploying...'
            }
        }
    }
}
