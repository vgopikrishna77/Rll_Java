pipeline {
    agent any

    parameters {
        choice(name: 'STAGE', choices: ['Build', 'Test', 'Deploy'])
    }
    tools {
        maven 'maven-3.9.16'
    }


    stages {
        stage('Build') {
            when {
                expression { params.STAGE == 'Build' }
            }
            steps {
                echo 'Building...'
                 dir('eLearning') {
                    sh 'mvn clean install -DskipTests'
                }
              
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
