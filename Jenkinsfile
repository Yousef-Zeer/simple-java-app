node{
    git branch: 'main', url: 'https://github.com/Yousef-Zeer/simple-java-project.git'
    stage('build'){
            try {
            sh'echo "build in progress"'

            }

            catch(Exception e)
            {
                 sh'echo "exception in progress"'
                throw e 
            }
    }

    stage('test')
    {
        if(env.BRANCH_NAME == "feat"){
           sh'echo "test stage"' 
        }
        else {
            sh'echo "skip test stage "'
        }
    }
}