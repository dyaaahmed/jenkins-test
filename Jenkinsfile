pipeline{
    agent any
    stages{
        stage('build'){
            steps{
                echo "building"
            }
        }
        stage('test'){
            steps{
                echo "testing"
            }
        }
        stage('deplpy'){
            steps{
                echo "deploying"
            }
        }
        post{
            always{
                echo "done"
            }
        }
    }
}
