pipeline {
    environment {
        TOKEN = 753253578c9764a224a4aea40c82de1e
      }
    agent {
        docker { image 'josedom24/debian-npm'
        args '-u root:root'
        }
    }
    stages {
        stage('Clone') {
            steps {
                git branch:'master',url:'https://github.com/angelsuarez1612/ic-html5.git'
            }
        }
        
        stage('Install surge')
        {
            steps {
                sh 'npm install -g surge'
            }
        }
        stage('Deploy')
        {
            steps{
                sh 'surge ./_build/ angelsuarez1612.surge.sh --token $TOKEN'
            }
        }
        
    }
}
