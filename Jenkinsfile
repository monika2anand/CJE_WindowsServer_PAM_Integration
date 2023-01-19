pipeline {
    agent {
        label 'PPS_Preprod'
    }
            
    environment {
        TEST02 = credentials('Application-CyberArk-admin-cje_poc1')
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
    post {  
         always {  
            // echo 'This will always run'  
         }  
         success {  
             echo 'CJE Windows server integration with PAM success'  
         }  
         failure {  
             mail bcc: '', body: "Failure in CJE Windows server integration with PAM", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Failure in CJE Windows server integration with PAM", to: "monika.anand@intel.com";  
         }  
         unstable {  
             mail bcc: '', body: "Failure in CJE Windows server integration with PAM", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "CJE Windows server integration with PAM", to: "monika.anand@intel.com";    
         }  
         changed {  
             echo 'This will run only if the state of the Pipeline has changed'  
             echo 'For example, if the Pipeline was previously failing but is now successful'  
         }  
     }  
    
    }