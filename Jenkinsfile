node {
   environment {
    CI = 'true'
    echo "Branch: ${env.BRANCH_NAME}"
  }

  stage('Git Checkout') {
    try {
        //git credentialsId: 'git-token', url: ''
        checkout scm
      } catch(err) {
         sh "echo error ao fazer checkout!"
      }
    }

  stage('Deploy Checkmarx') {
    try {
       step([$class: 'CxScanBuilder', comment: '', credentialsId: 'checkmarx', excludeFolders: '', excludeOpenSourceFolders: '', exclusionsSetting: 'global', failBuildOnNewResults: false, failBuildOnNewSeverity: 'HIGH', filterPattern: '', fullScanCycle: 10, groupId: '1', includeOpenSourceFolders: '', osaArchiveIncludePatterns: '*.zip, *.war, *.ear, *.tgz', osaInstallBeforeScan: false, password: '{AQAAABAAAAAQ+lKfBJCIXGQJO46So6BwbDqgbESjObKbaXw+c/FxVCE=}', preset: '36', projectName: 'webGoat-checkmarx', sastEnabled: true, serverUrl: 'http://checkmarx.alpargatas.com.br', sourceEncoding: '1', useOwnServerCredentials: true, username: '', vulnerabilityThresholdResult: 'FAILURE', waitForResultsEnabled: true])
      } catch(err) {
         sh "echo error ao fazer Deploy Checkmarx!"
      }
    }

}