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
    tools{
        // you may want to use some tools like maven gradle or jdk
        //if you want to make it avilable in jenkins go to jenkins >> settings >> global tools and add this tool
        // then you need to add it like this 
        maven 'Maven' // 'Maven is the name defined in jenkins'
    }
    parameters{
        //parametes must define in that way 
        // type_of_paramteres may be booleanParam , choice, etc (name: , defaultvalue: , description)
        boolean (name: parameter1 , defaultValue: true , decription: parmater1 )
        // you can use it with when {expressions{}}
        //or you can substitue in other things 
        //substitution param.parameter1 
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
                //steps: first you need to install credintial binding plugin and credintials plugin
                // define cred var in environment env
                // you also need to add cred in jenkins credintials
                //then you can specify cred in 

                // or you define credintial is specific stage using withCredintials([this will define object]) for ex
                withCredintials([
                    usernamePassword(credintials: 'id1', usernameVariables: USER1 , passwordVariable: PASS1)
                    // this will use cred with id1 and define variable USER1 with value of username in credintial stored in jenkins
                ]) {
                    // you can use these variables here for example 
                    sh "ssh ${USER1}@ip uptime"
                }
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
