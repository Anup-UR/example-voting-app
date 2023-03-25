pipeline{
    agent {label 'worker'}
    options{
        retry(2)
    }
    parameters{
        string(name: 'BRANCH', defaultValue: 'master')
        choice(name: 'ENVIRONMENT', choices: ['Dev','QA','PROD'])
    }
    stages{
        stage('First Stage'){
            steps{
                 sh "echo Beta"
            }
        }
        stage('Second Stage'){
            steps{
                sh "sleep 30" 
            }
        }
    }
    post{
        always{
            echo "Always Run"
        }
    }
}
