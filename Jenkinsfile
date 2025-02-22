pipeline {
   tools{
      jdk 'JAVA_HOME_L'
	  maven 'M2_HOME_L'
	  }
    agent { label 'linuxslv' }
	
     stages{
        stage('git checkout') {
            steps{
                 git 'https://github.com/kiran90-gh/maven.git'
              
            }
        }
        stage('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }
    }
}
