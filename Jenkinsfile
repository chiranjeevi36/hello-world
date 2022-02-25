pipeline {
    agent any
    environment {
        PATH="/opt/maven-3.8.4/bin:$PATH"
    }
    stages {
        stage('git cloning') {
            steps {
                git credentialsId: 'git_credentials', url: 'https://github.com/chiranjeevi36/hello-world.git'
            }
        }
        stage('build code') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('deploy app to tomcat') {
            steps {
                sshagent(['deploy']) {
                    sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/java-build-pipeline/webapp/target/webapp.war ubuntu@13.232.225.137:/opt/tomcat10/webapps"
}
            }
        }
    }
}
