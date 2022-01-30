node{

   def tomcatWeb = '${catalina.base}\\webapps'
   def tomcatBin = '${catalina.base}\\bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
     git 'https://github.com/abhinna1234/mvntest.git'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'MAVEN', type: 'maven'   
      "${mvnHome}\\bin\\mvn package"
   }
   stage('Check-war-file'){
      // Get maven home path
      bat "dir"
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
      bat "echo ${tomcatWeb}"
    
     "copy target\\mvntest.war \"${tomcatWeb}\\mvntest.war\""
   }
}
