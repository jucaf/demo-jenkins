//import com.evobanco.Utils

@Library(['demo-jenkins-library','demo-non-library']) _

def utils = new com.evobanco.Utils()
def mavenCmd = 'mvn -U -B -s /opt/evo-maven-settings/evo-maven-settings.xml'

node('maven') {

    stage('Checkout source code') {
        echo 'Checkout scm'
        checkout scm
    }

    stage('Credentials') {
        withCredentials([usernamePassword(credentialsId: 'demo-jenkins-credentials', passwordVariable: 'PASSWORD', usernameVariable: 'USERNAME')]) {
            echo "Username: ${USERNAME}"
            echo "Password: ${PASSWORD}"
        }
    }

    stage ('Detect branch type') {
        echo 'Detect branch type'
        def branchName = utils.getBranch()
        def branch_type = utils.getBranchType(branchName)

        echo "branchName: ${branchName}"
        echo "branchType: ${branch_type}"
    }


    stage('Compile') {
        echo 'Maven compile'
        sh "${mavenCmd} compile"
    }
}