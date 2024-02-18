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

          stage('Copy .env') {
            steps {
                echo ".env MENTIONED RRRAHHHHH" 
                sh '''
                cp /root/simple-apps/apps/.env apps/
                '''
            }
        }

        stage('Tseting') {
            steps {
                echo "Tsetingni" 
                sh '''
                cd apps
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
