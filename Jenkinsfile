pipeline {
    agent any
    tools {
        maven 'jenkinsmaven'
    }
    stages {
        stage('Get GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/PabloJeria8/AppPipelines.git'
            }
        }
        stage('Generate artifacts') {
            steps{
                echo 'Genera artefactos'
                sh 'mvn clean install'
            }
        }
        stage('storage artifacts'){
            steps{
                echo 'Almacenar artefactos'
                sh 'chmod 777 $PWD'
                sh 'chmod 777 /var/jenkins_home/workspace'
                sh 'chmod 777 /var/jenkins_home'
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: true , fingerprint: true
            }
        }
        stage('TESTS') {
            steps{
                echo 'Realiza Pruebas'
                sh 'mvn test '
            }
        }

    }
}
