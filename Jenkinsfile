pipeline {


    stages {
        agent {docker 'alpine/git'}
        stage('Checkout') {
            steps {
                git 'https://github.com/alphacentrino/spring-petclinic.git'
            }
        }
        stage('Build') {
        agent {docker 'maven:3.5-jdk-8-alpine'}
            steps {

                sh 'mvn clean package'
                junit '**/target/surefire-reports/TEST-*.xml'
            }
        }


    }
}
