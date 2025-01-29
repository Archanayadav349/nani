pipeline{
    agent any
    stages{
        stage(" the code from git"){
            steps{
                git branch: 'main', url: 'https://github.com/Archanayadav349/nani'
            }
        }
        stage("testing code"){
            steps{
            sh "mvn test"
          
           }
        }
        stage("build artifacts "){
            steps{
                sh "mvn package"
            }
        }
        stage("generate oa reports"){
            steps{
                sh "mvn pmd:pmd"
            }
        }
        stage("build artifacts using maven tool"){
            steps{
                sh "mvn package"
            }
        }
        stage(" deploying to tomcat"){
            steps{
                sshagent(['ec2-user']) {
    // some block
              sh "scp -o StrictHostKeyChecking=no target/arch12.war ec2-user@3.238.229.249:/home/tomcat9/webapps"
                    
                }
            }
        }
    }    
    
}
