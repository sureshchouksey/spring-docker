pipeline {
    agent any

    stages {
        stage ('Clone') {

            steps {
                withMaven(maven : 'apache-maven-3.6.1') {
<<<<<<< HEAD
                    bat 'mvn clean install -Dmaven.test.skip=true'
                    
=======
                    bat 'mvn clean compile'
>>>>>>> c00c203db492117aa9c821d51b30fdacc752db80
                }
            }
        }
        stage ('Docker') {

            steps {
<<<<<<< HEAD
                bat 'docker build -t springdocker:1.0 .'
=======
                withMaven(maven : 'apache-maven-3.6.1') {
                    bat 'mvn test'
                }
>>>>>>> c00c203db492117aa9c821d51b30fdacc752db80
            }
        }

        stage ('Run Docker') {
            
            steps {
<<<<<<< HEAD
                echo "${env.BRANCH_NAME}"
                def aliaceName = ${env.BRANCH_NAME}
                bat 'docker run --name spring{env.BRANCH_NAME} -d -p 8080 springdocker:1.0'
=======
                withMaven(maven : 'apache-maven-3.6.1') {
                    bat 'mvn deploy'
                }
>>>>>>> c00c203db492117aa9c821d51b30fdacc752db80
            }
        }

       
    }
}
