pipeline{
    agent any

    environment{
        VERCEL_TOKEN = credentials('react_vercel_token')
    }

    stages{
        stage('Install'){
            steps{
                bat 'npm install' 
            }
        }
        stage('Test'){
            steps{
                echo 'Skipping Tests - No tests found'
            }
        }
        stage('Build'){
            steps{
                bat 'npm run build'
            }
        }
        stage('Deploy'){
            steps{
                bat 'npx vercel --prod --yes --token "%VERCEL_TOKEN%" --project my-reactjs-app'
            }
        }
    }
}