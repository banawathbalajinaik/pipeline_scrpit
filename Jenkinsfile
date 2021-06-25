pipeline {
    agent any
    stages {
        stage('git_clone') {
            steps {
                sh '''
                rm -rf *
                git clone 'https://github.com/banawathbalajinaik/pipeline_scrpit.git'
                '''
            }
        }
        stage('mvn_clean') {
            steps {
                sh '''
                pwd
               mvn -f <pom.xml path> clean
                '''
            }
        }
        stage('mvn_compile') {
            steps {
                sh '''
                pwd
               mvn compile
                '''
            }
        }
        stage('mvn_test_cases') {
            steps {
                sh '''
                pwd
               mvn test
                '''
            }
        }
        stage('mvn_package') {
            steps {
                sh '''
                pwd
               mvn package
                '''
            }
        }
        stage('Sonar_Quality') {
            steps {
                sh '''
                pwd
               mvn sonar:sonar
                '''
            }
        }
    }
}
