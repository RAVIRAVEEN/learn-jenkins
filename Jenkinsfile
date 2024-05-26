pipeline {
    agent {
       node {
         label 'agent-1' 
     }
}
   environment { 
       GREETINGS = 'hello jenkins'
    }
    options {
        timeout(time: 1, unit: 'HOURS') 
          disableConcurrentBuilds() 
    }
//   build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                sh  """
                  echo "here i execute shell-scrpiting"
                  env "$greetings"

                """
            }
        }
    }

    //  post build 
     post { 
        always { 
            echo 'I will always say Hello again!'
        }
     

        failure {
            echo ' this runs when pipeline is failed used generally to send alerts'
        }
      
       success { 
            echo 'I will always say Hello when pipeline is success'
        }
   
    }

}