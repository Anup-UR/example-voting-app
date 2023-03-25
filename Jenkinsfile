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
        stage('Build Stage'){
            steps{
                 sh '''
                 cd vote
                 docker build .
                 '''
            }
        }
        stage('Deploy Stage'){
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
