variable=value // you can specify variable here and use it in pipeline, value may groovy script return boolean for ex
// and you can use it with when
// jenkins provide variables u can use , you can found it in jenkinsurl:8080/env-vars.html 
pipeline{
    agent any
    stages{
        stage('build'){
            // you can specify condition for example if you want to run this stage only in specific branch or you can specify if condition is true or false and you can define this condition
            when{
                expression{
                    // there are many predifined envs you can use for ex CURRENT_BRANCH
                    // or you can define variables and use it you can def vars in top of file before pipeline{}
                    env.CURRENT_BRANCH == master || env.CURRENT_BRANCH == master
                }
            }
            steps{
                echo "building"
            }
        }
        stage('test'){
            when{
                expression{
                    // there are many predifined envs you can use for ex CURRENT_BRANCH
                    // or you can define variables and use it you can def vars in top of file before pipeline{}
                    env.CURRENT_BRANCH = master && env.CURRENT_BRANCH = master
                }
            }
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
