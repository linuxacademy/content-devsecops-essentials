pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'ls -l'
      }
    }
    stage('Dependency Check') {
      steps {
        dependencyCheckAnalyzer(datadir: 'dependency-check-data', includeVulnReports: true, includeHtmlReports: true)
        dependencyCheckPublisher()
        archiveArtifacts(allowEmptyArchive: true, artifacts: '**/dependency-check-report.html')
      }
    }
  }
}