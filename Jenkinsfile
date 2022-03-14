pipeline {

    agent any 
         triggers {
        githubPush()
      }

    stages {
        stage("Get Branches from Git"){
            steps{
                     sh """
                        git tag > ${WORKSPACE}/TagList.txt
                        echo ${GITHUB_PR_TARGET_BRANCH}
                     """  
               }
            }
                
        stage ('tag Stage') {
            when { 
              allOf { 
                expression { env.GITHUB_PR_TARGET_BRANCH == "main" }
              } 
            }
            steps {
                  sh """
       # git tag -a some_tag -m 'Jenkins'
      #  git push ${GIT_URL} --tags
      cat dat.txt
      echo test
        """
              
            }
        }
    }
}
