variable=value // you can specify variable here and use it in pipeline, value may groovy script return boolean for ex
// and you can use it with when
// jenkins provide variables u can use , you can found it in jenkinsurl:8080/env-vars.html 
pipeline{
    agent any
    //you can define you own env variables like this 
    environment {
        NEW_ENV = '1.3.5'
        // for credintials
        SERVER_CRED = credintials(id) // id of credintial that you created in jenkins
    }
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
                // you can substitue value of env variable that you defined 
                ehco "${NEW_ENV}"
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
                // in order to connect to deploy server you need credintials
                //steps: first you need to install credintial binding plugin
                // define cred var in environment env
                // you also need to add cred in jenkins credintials
                //then you can specify cred in 
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
