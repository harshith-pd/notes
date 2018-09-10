pipeline{
  agent any
  stages{
    stage("get list of all jenkins_files"){
      steps{
        script{
          sh "ls > ${env.WORKSPACE}/groovy_snippets/dir.txt"
          result = readFile("${env.WORKSPACE}/groovy_snippets/dir.txt").trim()
          println (result)
        }
      }
    }
  }
}
