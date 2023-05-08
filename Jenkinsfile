pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps  {
                withMaven(maven : 'maven_3_9_1') {
                    bat 'mvn clean compile'
                     bat 'mvn install'
                }
            }
    

        stage ('Testing Stage') {
            steps  {
                withMaven(maven : 'maven_3_9_1') {
                    bat 'mvn test'
                }
            }
        }

        stage ('Sonar Scan') {
        steps {
            withSonarQubeEnv('Sonar_Qube') {
                bat 'mvn sonar:sonar'

                }
            }
        }
    }
}
