pipeline{
    agent any
    tools{
        maven 'M2_HOME'
    }
    stages{
         stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('GIT') {
            steps {
                git branch: 'master', 
                    url: 'https://github.com/tamim-hmizi/avec-maven.git',
                    credentialsId: '421f578a-8360-4777-a60b-926fec1d0647'
            }
        }
        stage('MAVEN') {
            steps {
                script {
                   bat 'mvn -v'
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}