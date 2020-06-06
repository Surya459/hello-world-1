pipeline {
    agent any
    
    parameters{
    string(name:'Greeting',defaultValue:'Hello', description:'How Should I greet the world?')
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
        stage('Greet') {
            steps{
            echo '$(params.Greeting) world!'
            }
        }
}
}
