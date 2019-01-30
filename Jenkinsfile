//START-OF-SCRIPT
timeout(time: 60, unit: 'SECONDS') {
    node('agent1') {
        def GRADLE_HOME = tool name: 'gradle-4.10.2', type: 'hudson.plugins.gradle.GradleInstallation'
        sh "${GRADLE_HOME}/bin/gradle tasks"

        stage('Clone') {
            git url: 'https://github.com/jeremycook123/devops-webapp1.git'                
        }

        stage('Build') {
            sh "${GRADLE_HOME}/bin/gradle build"
        }

        stage('Archive') {
          archiveArtifacts 'build/libs/*.war'
       }
    }
}    
//END-OF-SCRIPT
