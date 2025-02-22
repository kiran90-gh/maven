pipeline {
   tools{
      jdk 'JAVA_HOME_WIN'
	  maven 'M2_HOME_WIN'
	  }
    agent { label 'winslv' }
	
     stages{
        stage('git checkout') {
            steps{
                 git 'https://github.com/kiran90-gh/maven.git'
              
            }
        }
        stage('compile') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('package') {
            steps {
                bat 'mvn package'
            }
        }
    }
}
