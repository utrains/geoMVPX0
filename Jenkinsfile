pipeline {
    agent any

// adding tools to get the job done, this help us to run maven commands

tools {
  maven 'M2_HOME'
}

  //  this will be the trigger for this jon
  triggers {
  pollSCM '* * * * *'
}

    
     stages{
     
      stage('Maven'){
        // maven commands to perform tasks on out code
       steps {

        sh 'mvn clean'
        sh 'mvn install'
        sh 'mvn package'

        //  echo "Hello World"
         
       }
    }
    stage('test'){
       steps {
        //  echo "Development"
                sh 'mvn test'

           sleep 4
       }
    }
    stage('Testing'){
       steps {
         echo "Testing"
           sleep 4
       }
    }
    stage('QA Testing'){
       steps {
         echo "QA Testing"
           sleep 4
       }
    }
    stage('Deploy'){
       steps {
         echo "Deploy"
           sleep 4
       }
    }
    stage('Production'){
       steps {
         echo "Production"
           sleep 4
       }
    }
    
    }

}
