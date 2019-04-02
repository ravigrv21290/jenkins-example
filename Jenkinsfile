
def mvnHome    
pipeline {
    agent any
   
    stages {
        stage ('Compile Stage') {
           
            steps {
                withMaven(maven : 'apache-maven-3.6.0') {
                    bat 'mvn clean test'               
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'apache-maven-3.6.0') {
                    bat 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'apache-maven-3.6.0') {
                    bat 'mvn deploy'
                }
            }
        }
    }
}
