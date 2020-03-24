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
    stage('MOVING_JAR')
    {
	sh 'mkdir myarchieves/$JOB_NAME/$BUILD_ID-$(date +%F_%H:%M:%S)'
        sh 'cp -r target/*.jar myarchieves/$JOB_NAME/$BUILD_ID-$(date +%F_%H:%M:%S)'
    }
}
