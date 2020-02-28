node{

   def tomcatWeb = 'E:\\Apache_Software_Foundation\\Tomcat-8.5\\webapps'
   def tomcatBin = 'E:\\Apache_Software_Foundation\\Tomcat-8.5\\bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
     git 'https://github.com/muley25/mydemo.git'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'maven-3', type: 'maven'   
      bat "${mvnHome}/bin/mvn package"
      }
   stage('Deploy to Tomcat'){
     bat "copy target\\Hello-World.war \"${tomcatWeb}\\Hello-World.war\""
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         bat "${tomcatBin}\\startup.bat"
         sleep(time:20,unit:"SECONDS")
   }
}
