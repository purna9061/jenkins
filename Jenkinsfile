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
    stage('ContinonusDeplotment')
        {
            deploy adapters: [tomcat9(credentialsId: '5ee80f88-386e-438c-83ea-cb638a4d6b09', path: '', url: 'http://172.31.17.0:8080')], contextPath: 'testapp', war: '**/*.war'
        }

    stage('ContinonusTesting')
        {
            git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
            sh 'java -jar /var/lib/jenkins/workspace/scriptedpipeline1/testing.jar'

        }
    stage('ContinonusDelivary')
        {
        deploy adapters: [tomcat9(credentialsId: '5ee80f88-386e-438c-83ea-cb638a4d6b09', path: '', url: 'http://172.31.23.238:8080')], contextPath: 'prodapp', war: '**/*.war'
        }

}

