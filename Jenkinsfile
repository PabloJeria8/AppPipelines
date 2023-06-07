pipeline {
    agent any
    tools {
        maven 'jenkinsmaven'
    }
    stages {
        stage('Get GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/PabloJeria8/AppPipelines.git'
                sh 'mvn clean package'
            }
        }
    }
}
