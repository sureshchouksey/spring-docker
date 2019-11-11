pipeline {
    agent any

    stages {
        stage ('Clone') {

            steps {
                withMaven(maven : 'apache-maven-3.6.1') {
                    bat 'mvn clean install -Dmaven.test.skip=true'
                    
                }
            }
        }
        stage ('Docker') {

            steps {
                bat 'docker build -t springdocker .'
            }
        }

       
    }
}
