node{

   def tomcatWeb = 'C:\\Users\\VINOD KUMAR\\.jenkins\\workspace\\IDBI\\target'
   def tomcatBin = 'D:\\apache-tomcat-9.0.65\\bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
     git 'https://github.com/mannepallyvinod/IDBI.git'
   }
   stage('Compile-Package-create-jar-file'){
      // Get maven home path
      def mvnHome =  tool name: 'Maven', type: 'maven'   
      bat "${mvnHome}/bin/mvn package"
      }
/*   stage ('Stop Tomcat Server') {
               bat ''' @ECHO OFF
               wmic process list brief | find /i "tomcat" > NUL
               IF ERRORLEVEL 1 (
                    echo  Stopped
               ) ELSE (
               echo running
                  "${tomcatBin}\\shutdown.bat"
                  sleep(time:10,unit:"SECONDS") 
               )
'''
   }*/
   stage('Deploy to Tomcat'){
     bat "copy C:\\Users\\VINOD KUMAR\\.jenkins\\workspace\\IDBI\\target\\IDBI-1\"${tomcatWeb}\\IDBI-1\""
   }
      stage ('Start Tomcat Server') {
         sleep(time:5,unit:"SECONDS") 
         bat "${tomcatBin}\\startup.bat"
         sleep(time:100,unit:"SECONDS")
   }
}
