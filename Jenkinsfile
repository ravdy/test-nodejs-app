pipeline { 
  
   agent any
  environment{
    script {
        if (env.BRANCH_NAME == 'dev') {
        // Deploy to dev server
          sh 'echo "dev deploymebnt"'
          DEV_ENV = 'devserver_ip'
           
        }
    }
  }

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'echo "Install Dependencies ${DEV_ENV} ${GIT_URL}"'
           script{
             echo "Current branch: Dunkins_${env.BRANCH_NAME}_env"
             echo "Git repo: ${env.GIT_URL}"
           }
        }
     }
     stage('Checkout') {
            steps {
                // Automatically checks out the source code for the branch that triggered the build
                checkout scm
            }
        }
     
     // stage('Git Clone') { 
     //        steps {
     //            // Git clone step
     //            script{
     //              // git branch: "${env.BRANCH_NAME}", credentialsId: 'git-hub', URL: "${env.GIT_URL}"
     //              git branch: "${env.BRANCH_NAME}", credentialsId: 'git-hub', URL: 'https://github.com/ashirwad8858/test-nodejs-app-jenkins-pipline.git'

     //            }
     //        }
     //    }
     
     stage('Test') { 
       when {
                branch 'dev'
            }
        steps { 
           sh 'echo "testing application..."'
        }
      }
     stage('Test') { 
       when {
                branch 'qa'
            }
        steps { 
           sh 'echo "testing application..."'
        }
      }
     stage('Docker Build') {
            steps {
                // Docker build step
                script {
                    docker.build("your-image-name:${env.BRANCH_NAME}")
                }
            }
        }

         stage("Deploy application") { 
         steps {
                // Deploy step
                script {
                    if (env.BRANCH_NAME == 'dev') {
                        // Deploy to dev server
                        sh 'echo "dev deploymebnt"'
                    } else if (env.BRANCH_NAME == 'qa') {
                        // Deploy to qa server
                        sh 'echo "qa deploymebnt"'
                    } else if (env.BRANCH_NAME == 'stage') {
                        // Deploy to stage server
                        sh 'echo "stage deploymebnt"'
                    }
                }
            }

     }
  
   	}

   }
