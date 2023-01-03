pipeline {
   agent any 
   environment { 
      mvnhome = "C:\\apache-maven-3.8.6\\bin:$mvnhome"
   }
   stages {
      stage ("Checkout") {
         steps {
         git url: "https://github.com/mannepallyvinod/IDBI.git"
        }
      }
     stage ("Build") {
         steps {
         bat "mvn clean package"
        }
     }
      stage ("Copy") {
         steps {
            bat "target\\IDBI-1.jar D:\\apache-tomcat-9.0.65\\webapps"
         }
      }
   }
}
