pipeline {

  environment {
    registry = "venkateshpakanati/devops"
    registryCredential = 'batmeyou007'
    dockerImage = ''
   // def app
  }

  agent any
  
  stages {
   /* stage('Cloning Git') {
     steps {
      git 'https://github.com/gustavoapolinario/microservices-node-example-todo-frontend.git'
     }
    }  */
   stage('Building image') {
      steps{
        script {
         docker.build(registry + ":$BUILD_NUMBER")
        }
      }
    }
 /*   stage('Test image') {
        
        app.inside {
            sh 'echo "Tests passed"'
        }
    } */
 
  stage('Deploy Image') {
   steps{
    script {
      //docker.withRegistry('https://cloud.docker.com/', registryCredential ) {
    //    dockerImage.push()
      docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
          dockerImage.push()
        //    app.push("${env.BUILD_NUMBER}")
        //    app.push("latest")
      }
    }
   }
  }
  
/*  stage('Remove Unused docker image') {
   //   steps{
      //  sh "docker rmi $registry:$BUILD_NUMBER"
   //   }
    } */
 }
}
