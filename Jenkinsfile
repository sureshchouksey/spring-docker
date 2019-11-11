pipeline {
    agent any

    stages {
        stage ('Clone') {

            steps {
                withMaven(maven : 'apache-maven-3.6.1') {
                    bat 'mvn package'
                    bat 'java -jar target/websocket-demo-0.0.1-SNAPSHOT.jar'
                }
            }
        }

       
    }
}
