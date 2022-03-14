pipeline {

    agent any 
    stages {
        stage("Get Branches from Git"){
            steps{
                     sh """
                        git tag > ${WORKSPACE}/TagList.txt
                     """  
               }
            }
                
        stage ('tag Stage') {

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
