pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
        timeout(time: 1, unit: 'HOURS')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
		sh 'mvn clean install -DskipTests'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
		sh 'mvn clean test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
		sh 'java -jar target/demo-0.0.1-SNAPSHOT.jar'
            }
        }
    }
}
