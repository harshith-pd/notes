pipeline{
    agent any
    stages{
        stage("Checkout"){
            steps{
                script{
                        echo "${getChangeString()} is the changeset"
                        sh "git rev-list --all --remotes"
                        }
                    }
                }
            }
        }

@NonCPS
def getChangeString() {
    MAX_MSG_LEN = 100
    def changeString = ""

    echo "Gathering SCM changes"
    def changeLogSets = currentBuild.changeSets
    echo "${changeLogSets}"
    for (int i = 0; i < changeLogSets.size(); i++) {
        def entries = changeLogSets[i].items
        for (int j = 0; j < entries.length; j++) {
            def entry = entries[j]
            echo "${entry.commitId} by ${entry.author} on ${new Date(entry.timestamp)}: ${entry.msg}"
            def files = new ArrayList(entry.affectedFiles)
            for (int k = 0; k < files.size(); k++) {
                def file = files[k]
                changeString += "${file.path}\n"
            }
        }
    }

    if (!changeString) {
        changeString = " - No new changes"
    }
    return changeString
}