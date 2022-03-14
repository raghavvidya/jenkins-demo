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
withCredentials() {
    sh("git tag -a some_tag -m 'Jenkins'")
    sh("git push ${GIT_URL} --tags")
            }
              
            }
        }
}
