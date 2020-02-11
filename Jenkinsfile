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
                echo "(before init) SLEEP_FOR: $SLEEP_FOR"
                sh "source .env"
                echo "(after init) SLEEP_FOR: $SLEEP_FOR"
            }
        }
        stage('design') {
            steps {
                echo "SLEEP_FOR: $SLEEP_FOR"
                sh 'echo "SLEEP_FOR (in sh): $SLEEP_FOR"'
                sh "sh ./design.sh"
            }
        }
        stage('build') {
            steps {
                sh "sh ./build.sh"
            }
        }
        stage('test') {
            steps {
                sh "sh ./test.sh"
            }
        }
        stage('deploy') {
            steps {
                sh "sh ./deploy.sh"
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