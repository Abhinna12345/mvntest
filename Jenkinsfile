node{

   def tomcatBin = '${CATALINA_HOME}\\bin'
   def tomcatStatus = ''
   stage('SCM Checkout'){
     git 'https://github.com/abhinna1234/mvntest.git'
   }
   stage('Compile-Package-create-war-file'){
      // Get maven home path
      def mvnHome =  tool name: 'MAVEN', type: 'maven'   
      bat "mvn package"
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
      bat "echo ${CATALINA_HOME}"
      bat "echo ${tomcatWeb}"
      bat "dir target"
     bat "copy target\\mvntest.war \"${${CATALINA_HOME}}\\webapps\\mvntest.war\""
   }
}
