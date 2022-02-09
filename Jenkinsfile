pipeline {
    agent { label 'jdk-mvn' }
    triggers { 
        cron('45 23 * * 1-5')
        pollSCM('*/5 * * * *')
    }
    parameters {
        string(name: 'MAVEN_GOAL', defaultValue: 'package', description: 'This is maven goal' )
    }
    stages {
        stage('scm') {
            steps {
                git url: 'https://github.com/navr24396/java11-examples.git'
            }
        }
        stage('build') {
            steps {
                sh "/home/fnd/mavenfolder/apache-maven-3.8.4/bin/mvn ${params.MAVEN_GOAL}"
            }
        }
    }
}