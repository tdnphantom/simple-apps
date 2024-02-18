pipeline {
    agent {
        node {
            label 'devops1-puja'
        }
    }

    stages {
        stage('Buldi') {
            steps {
                echo "Buildingi" 
                sh '''
                cd apps
                npm install
                '''
            }
        }

        stage('Tseting') {
            steps {
                echo "Tsetingni" 
                sh '''
                npm test
                npm run test:coverage
                '''
            }
        }

        stage('Scannign') {
            steps {
                echo "Snaccing" 
            }
        }

        stage('Cocnaineridez') {
            steps {
                echo "Corantizer" 
            }
        }

        stage('Depyol') {
            steps {
                echo "Delpoyinh" 
            }
        }

        stage('Pulibsh') {
            steps {
                echo "Pbulish" 
            }
        }
    }
}
