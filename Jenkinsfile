pipeline {
    agent any

    options {
        office365ConnectorWebhooks([[
            name: 'Office 365',
            startNotification: true,
            notifySuccess: true,
            notifyFailure: true,
            notifyAborted: true,
            notifyNotBuilt: false,
            notifyUnstable: true,
            notifyRepeatedFailure: true,
            notifyBackToNormal: true,
            adaptiveCards: true,
            url: 'https://prod-91.westus.logic.azure.com:443/workflows/5cd2c73ee2d8442aba1a68973d4f0ddc/triggers/manual/paths/invoke?api-version=2016-06-01&sp=%2Ftriggers%2Fmanual%2Frun&sv=1.0&sig=27OBttiifLqn9tQXALwutxYO2af2yKE_0Pii9x3FlUo'
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
            }
            exit 1
        }
    }
}
