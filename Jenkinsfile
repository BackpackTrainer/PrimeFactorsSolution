pipeline {
    agent any

    stages {
        stage ('Compile Stage') {
            steps  {
                withMaven(maven : 'maven_3_9_1') {
                    bat 'mvn clean compile'
                }
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
            withSonarQubeEnv(installationName : 'Sonar_Qube') {
                bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.9.1.2184:sonar'
                }
            }
        }
    }
}
