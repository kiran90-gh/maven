pipeline{
 tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
     agent any
	  
	  stages{
	  
	  stage("checkout"){
	   steps{
	   git 'https://github.com/kiran90-gh/maven.git'
	   }
	                  }
	
	   stage("compile"){
	    steps{
		 sh 'mvn compile'
		}
		}
       stage("test"){
	    steps{
		 sh 'mvn test'
		}
		}
       stage("package"){
	    steps{
		 sh 'mvn clean package'
                 sh "mv target/*.jar target/myweb.war"

		}
		}
		   stage("deploy"){
     steps{
   
        sshagent(['4f0ad75c-c38f-4567-88a5-769f83acffa7']) 
     {
    

    
   
        sh """
                 
            scp -o StrictHostKeyChecking=no target/myweb.war ec2-user@3.110.41.150:/home/ec2-user/tomcat10/webapps/

              ssh ec2-user@3.110.41.150 /home/ec2-user/tomcat10/bin/shutdown.sh
              ssh ec2-user@3.110.41.150 /home/ec2-user/tomcat10/bin/startup.sh
            
          
          """



    // some block
}
  }
  }
   }
 }
