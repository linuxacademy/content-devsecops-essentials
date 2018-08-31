pipeline {
    agent { docker { image 'webgoat/webgoat-7.1' } }
    stages {
        stage('build') {
            steps {
                sh 'ls -l'
            }
        }
        stage("Dependency Check") {
            steps{
   			        dependencyCheckAnalyzer datadir: 'dependency-check-data', includeVulnReports: true, hintsFile: '', includeCsvReports: false, includeHtmlReports: true, includeJsonReports: false, isAutoupdateDisabled: false, outdir: '', scanpath: '', skipOnScmChange: false, skipOnUpstreamChange: false, suppressionFile: '', zipExtensions: ''
                
    		        dependencyCheckPublisher canComputeNew: false, defaultEncoding: '', healthy: '', pattern: '', unHealthy: ''

            		archiveArtifacts allowEmptyArchive: true, artifacts: '**/dependency-check-report.html'

            }
        }            
    }
}
