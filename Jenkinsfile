//START-OF-SCRIPT
node {
    def GRADLE_HOME = tool name: 'gradle-4.10.2', type: 'hudson.plugins.gradle.GradleInstallation'
    sh "${GRADLE_HOME}/bin/gradle tasks"

    stage('Clone') {
        git url: 'https://github.com/cloudacademy/devops-webapp.git'                
    }

    stage('Build') {
        sh "${GRADLE_HOME}/bin/gradle build -PwarName=webapp.war --info"
    }
    
    stage('Archive') {
      archiveArtifacts 'build/libs/*.war'
   }
}
//END-OF-SCRIPT