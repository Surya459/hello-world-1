pipeline {
    agent any
    
    parameters{
    string(name:'Greeting',defaultValue: 'Hello', Description: 'How Should I greet the world?')
    }
    

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        Stage('Greet') {
            Steps{
            echo '$(params.Greeting) world!'
    }
        }
}
