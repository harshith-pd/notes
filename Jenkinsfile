pipeline{
  agent any
  stages{
    stage("get list of all jenkins_files"){
      steps{
        script{
          sh "ls > ${env.WORKSPACE}/groovy_snippets/dir.txt"
          result = readFile("${env.WORKSPACE}/groovy_snippets/dir.txt").trim()
          for (item in result.tokenize('\n')){
            if fileExists("${env.WORKSPACE}/groovy_snippets/${item}/Jenkinsfile"){
            println ("Jenkins file found at" + "${env.WORKSPACE}/groovy_snippets/${item}")
            }
            else{
            println ("No jenkins file found at" + "${env.WORKSPACE}/groovy_snippets/${item}")
            }
          }
        }
      }
    }
  }
}
