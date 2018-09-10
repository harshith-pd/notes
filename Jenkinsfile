import static groovy.io.FileType.FILES

pipeline{
  agent any
  stages{
    stage("get list of all jenkins_files"){
      steps{
        script{
          def dir = new File(".");
          def files = [];
          dir.traverse(type: FILES, maxDepth: 0) { files.add(it) };
          println (files)
        }
      }
    }
  }
}
