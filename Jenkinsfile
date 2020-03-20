node('Spring')
{
    stage('VCS')
    {
        git 'https://github.com/pgottipalli/jenkinsrepo.git'
    }
    stage('PACKAGING')
    {
        sh 'mvn clean package'
    }
    stage('ARCHIVING')
    {
        archive 'target/*.jar'
    }
    stage('LOGS')
    {
        junit '/target/surefire-reports/*.xml'
    }
}
