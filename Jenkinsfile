node('built-in')
{
    stage('ContinonusDownload')
        {
            git 'https://github.com/purna9061/jenkins.git'
        }
    stage('ContinonusBuild')
        {
            sh 'mvn package'
        }
    stage('COntinonusDeploy')
        {
            sh 'scp /var/lib/jenkins/workspace/scriptedpipeline1/webapp/target/webapp.war ubuntu@172.31.19.87:/var/lib/tomcat9/webapps/testapp.war'
        }

}

