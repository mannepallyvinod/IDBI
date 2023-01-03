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
   }
}
