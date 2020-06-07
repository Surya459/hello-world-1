

pipeline {
    agent any
    environment{
    NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('github-surya')
    }
    tools{
     maven 'maven-jenkins'
    }
    
    parameters{
    string(name:'Greeting',defaultValue:'Hello', description:'How Should I greet the world?')
        choice(name:'Intent',choices: ['low','high','thope'],description: 'just playing around')
        booleanParam(name: 'Executedeploy', defaultValue: true, description: 'to deploy or not')
    }
    

    stages {
        stage('Build') {
          
            steps {
                echo 'Building..'
                echo "Building version: ${NEW_VERSION}"
                
                echo 'Building version: ${NEW_VERSION}'
                
                sh "mvn install"
            }
        }
        stage('Test') {
            
            when{
                
                expression{
                
                    BRANCH_NAME == 'development'
                }
            
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            when{
                expression{
                params.Executedeploy
                }
            }
            steps {
                echo 'Deploying....'
                echo "Deploying with ${SERVER_CREDENTIALS}"
                echo "Deploying with intent:${params.Intent}"
            }
        }
        stage('Greet') {
            steps{
                echo "${params.Greeting} world!"
                
                echo 'added webhook'
            }
        }
}
    
    post{
        always{
            echo 'the job is ran'
              }
        
        success{
              
            echo 'the job is sucess'
               }
          failure{
              
            echo 'the job is failure'
               }
        }
}
