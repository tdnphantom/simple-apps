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
                sh '''
                cd apps
                sonar-scanner   -Dsonar.projectKey=simple-apps   -Dsonar.sources=.  -Dsonar.host.url=http://172.23.10.12:9000   -Dsonar.login=sqp_ce3ef08d64e890b96cc9b780c526fb48deb1c2a1
                '''
            }
        }

        stage('Cocnaineridez') {
            steps {
                echo "Buliding Compoze dokcer" 
                sh '''
                docker compose build
                '''
            }
        }

        stage('Depyol') {
            steps {
                echo "Delpoyinh" 
                sh '''
                docker compose up -d
                '''
            }
        }

        stage('Pulibsh') {
            steps {
                echo "Pbulish" 
            }
        }
    }
}
