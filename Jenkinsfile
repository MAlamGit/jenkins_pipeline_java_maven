node {
   // Mark the code checkout 'stage'....
   stage 'Checkout'
   
   git 'https://github.com/MAlamGit/jenkins_pipeline_java_maven.git'

   // Get the maven tool.
   // ** NOTE: This 'M3' maven tool must be configured
   // **       in the global configuration.           
 
   // Mark the code build 'stage'....
   stage 'Build'
   // Run the maven build
   sh "$mvn -Dmaven.test.failure.ignore clean package"
   step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}
