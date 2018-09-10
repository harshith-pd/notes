pipeline{
  agent any
  stages{
    stage("get list of all jenkins_files"){
      steps{
        script{
        new File(".").eachDir() { dir ->
            println dir.getPath()
            }
        }
      }
    }
  }
}
