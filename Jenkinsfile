def mvnHome    
pipeline {
    agent any
   
    stages {
        stage ('Compile Stage') {
           
            steps {
                withMaven(maven : 'apache-maven-3.6.0') {
                    bat(/"${mvnHome}\bin\mvn" -Dintegration-tests.skip=true clean package/)

                        junit '**//*target/surefire-reports/TEST-*.xml'

                        archive 'target*//*.jar'                }
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
