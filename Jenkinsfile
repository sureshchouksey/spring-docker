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
                bat 'docker build -t springdocker:1.0 .'
            }
        }

        stage ('Run Docker') {
            
            steps {
                echo "${env.BRANCH_NAME}"
                echo "${currentBuild.number}"
                bat ("docker stop spring${env.BRANCH_NAME}${currentBuild.number}")
                bat ("docker rm spring${env.BRANCH_NAME}${currentBuild.number}")
                bat ("docker run --name spring${env.BRANCH_NAME}${currentBuild.number} -d -p 8080 springdocker:1.0")
                //echo "docker ps | grep spring${env.BRANCH_NAME} | sed 's/.*0.0.0.0://g' | sed 's/->.*//g'"
            }
        }

       
    }
}
