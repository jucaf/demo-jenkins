//import com.evobanco.Utils

//def utils = new com.evobanco.Utils()
def mavenCmd = 'mvn -U -B -s /opt/evo-maven-settings/evo-maven-settings.xml'

node('maven') {

    stage('Checkout source code') {
        echo 'Checkout scm'
        checkout scm
    }

/*
    stage ('Detect branch type') {
        echo 'Detect branch type'
        def branchName = utils.getBranch()
        def branch_type = getBranchType(branchName)
    }
*/

    stage('Compile') {
        echo 'Maven compile'
        sh '${mavenCmd}compile'
    }
}