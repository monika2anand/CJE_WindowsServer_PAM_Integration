pipeline {
    agent {
        label 'PPS_Preprod'
    }
            
    environment {
        TEST02 = credentials('Application-CyberArk-admin-cje_poc')
    }
    stages{
            stage('Verify PAM connection') {
            steps {
                script {
                    println "TEST02 USR: " + "${TEST02_USR}".substring(0, 7)
                    println "TEST02 PSW: " + "${TEST02_PSW}".substring(0, 6)
                }
            }
        }
        }
    
    }