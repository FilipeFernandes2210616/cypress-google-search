pipeline {
      agent any
      tools {nodejs "app"}

      stages {
        stage('Build/Deploy app to staging') {
            steps {
              echo "installing app"
              sh 'npm install'
            }
        }
        
        stage('Run automated tests'){
            steps {
              echo "Running automated tests"
            }
        }

        stage('SonarQube analysis') {
          steps {
                echo "SonarQube analysis"
            }
        }

        stage('JMeter Test') {
            steps {
                echo "JMeter Test"
            }
        }

        stage('Perform manual testing...'){
            steps {
                timeout(time: 2, unit: 'DAYS') {
                    input 'Proceed to production?'
                }
           }
        }

        stage('Release to production') {
            steps {
            // similar procedure as in the 'Build/ Deploy to staging' stage, suppressed here for cost saving purposes
                echo "Deploying app in production environment"
           }
        }
    }
}