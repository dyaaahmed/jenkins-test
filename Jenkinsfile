pipeline{
    agent any
    stages{
        stage('build'){
            // you can specify condition for example if you want to run this stage only in specific branch or you can specify if condition is true or false and you can define this condition
            when{
                expression{
                    // there are many predifined envs you can use for ex CURRENT_BRANCH
                    // or you can define variables and use it you can def vars in top of file before pipeline{}
                    env.CURRENT_BRANCH = master
                }
            }
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
            onfailure{
                echo "fail"
            }
            success{
                echo "sucess"
            }
        }
    }
}
