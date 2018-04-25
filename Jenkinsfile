pipeline {
    agent any
    tools {
        maven 'maven_3_0_5'
    }
    stages {
        stage ('Compile Stage') {

            steps {                
                    bat 'mvn clean compile'                
            }
        }

        stage ('Testing Stage') {

            steps {                
                    bat 'mvn test'                
            }
        }
        stage ('server:Results'){
            steps{
                junit '**ui-tests-testng/target/surefire-reports/TEST-*.xml'
                archive 'target/*.jar'            
            }
        }
       
    }
}
