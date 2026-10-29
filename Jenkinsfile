pipeline {
    agent { label 'devops1-agung' }

    stages {
        stage('Pull SCM') {
            steps {
                git branch: 'main', url: 'https://github.com/AgungAdityatama/idn-simple-apps.git'
            }
        }
        
        stage('Build') {
            steps {
                sh'''
                cd apps
                npm install
                '''
            }
        }
        
        stage('Testing') {
            steps {
                sh'''
                cd apps
                npm run test:coverage
                '''
            }
        }
        
        stage('Code Review') {
            steps {
                sh'''
                cd apps
                sonar-scanner \
                    -Dsonar.projectKey=idn-simple-apps \
                    -Dsonar.sources=. \
                    -Dsonar.host.url=http://172.23.13.86:9000 \
                    -Dsonar.token=sqp_33ce22003ee0f7ef9a01250d296c7bc6e607115c
                '''
            }
        }
        
        stage('Deploy') {
            steps {
                sh'''
                docker compose up --build -d
                '''
            }
        }
        
        
    }
}