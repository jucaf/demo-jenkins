pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                input {
                    message "Should we continue?"
                    ok "Yes, we should."
                    submitter "alice,bob"
                    parameters {
                        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                    }
                }
                echo "Hello, ${PERSON}, nice to meet you."
            }
        }
    }
}