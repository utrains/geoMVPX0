pipeline{
    agent any
    tools {
        maven 'M2_HOME'
    }
    stages{
        stage( 'mavin build' ){
            steps{
                sh 'mvn clean install package'
            }
        }

    stage( 'upload artifact' ){
            steps{
                script{
                    def mavenPom = readMavenPom file: 'pom.xml'
                    nexusArtifactUploader artifacts: 
                    [[artifactId: '${mavenPOM.artifactId}',
                    classifier: '',
                    file: "target/${mavenPOM.artifactId}-${mavenPOM.version}.${mavenPOM.packaging}",
                    type: "${POM_PACKAGING}"]], 
                    credentialsId: 'NexusID', 
                    groupId: "${mavenPOM.groupId}", 
                     nexusUrl: '45.56.67.125:8081', 
                      nexusVersion: 'nexus3', 
                       protocol: 'http', 
                        repository: 'bio-med',
                         version: "${mavenPom.version}"
                }
            }
    }
    stage( 'list the dir' ){
            steps{
                sh 'ls'
            }
    }
}