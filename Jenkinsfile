pipeline {
    agent any

    stages {
        
        stage('Checkout') {
            agent {docker 'alpine/git'}
            steps {
                git 'https://github.com/alphacentrino/spring-petclinic.git'
            }
        }
        stage('Build') {
        agent {docker 'maven:3.5-alpine'}
            steps {

                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }


    }
}
