pipeline {
    agent any

    options {
        teamsNotification([[
            name: 'Trial',
            startNotification: true,
            notifySuccess: true,
            notifyFailure: true,
            notifyAborted: true,
            notifyNotBuilt: false,
            notifyUnstable: true,
            notifyRepeatedFailure: true,
            notifyBackToNormal: true,
            conversation: '{"conversationId": "a:1M8TBL2LqarOpihAzn_4xFy-xiAZfBGPZqx2GEjtCMR0-Try5yTTrXV8Z-mQ5xPp3mrRVcAB094SNOFqHGO02ieYdGxjIIVtvziAXdnIY2Egx-hNffDKyxD-TD4R3A2Qb","teamId": "","conversationType": "personal","serviceURL": "https://smba.trafficmanager.net/amer/1362721f-1a09-474d-9d91-d6de38146d5f/"}'
        ]])
    }
    
    stages {
        stage('Build') {
            steps {
                echo "Building the project..."
            }
        }
        stage('Test') {
            steps {
                echo "Running tests..."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying the application..."
                exit 1
            }
        }
    }
}
