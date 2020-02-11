pipeline {
    agent any

    stages {
        stage('git-checkout') {
            steps {
                git 'https://github.com/AluBhorta/jenkins-pipeline-demo.git'
            }
        }
        stage('init-env') {
            steps {
                sh "env.sh"
            }
        }
        stage('design') {
            steps {
                sh "design.sh"
            }
        }
        stage('build') {
            steps {
                sh "build.sh"
            }
        }
        stage('test') {
            steps {
                sh "test.sh"
            }
        }
        stage('deploy') {
            steps {
                sh "deploy.sh"
            }
        }
    }

    post {
        always {
            sh 'echo "post:always @ `date`"'
        }
        success {
            sh 'echo "post:success @ `date`"'
        }
        failure {
            sh 'echo "post:failure @ `date`"'
        }
        unstable {
            sh 'echo "post:unstable @ `date`"'
        }
        changed {
            sh 'echo "post:changed @ `date`"'
        }
    }
}