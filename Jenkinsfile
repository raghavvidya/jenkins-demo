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
                     """  
               }
            }
                
        stage ('tag Stage') {
            when { 
              allOf { 
                expression { env.GITHUB_PR_STATE == "CLOSE" }
                expression { env.GITHUB_PR_TARGET_BRANCH == "master" }
                expression { env.GITHUB_PR_SOURCE_BRANCH == "hotfix/foo" }
              } 
            }
            steps {
                  sh """
       # git tag -a some_tag -m 'Jenkins'
      #  git push ${GIT_URL} --tags
      cat dat.txt
        """
              
            }
        }
    }
}
