node {

    currentBuild.result = "SUCCESS"
    
    try {
       
       stage('Checkout'){
          checkout scm
       }

       stage('Install'){
         sh 'node -v'
         sh 'npm prune'
         sh 'npm install'
         sh 'npm run test'
       }

       stage('Test'){
         sh 'npm run lint'
         sh 'npm run test'
       }

       stage('Build'){
            sh 'npm run build'
       }

       stage('Cleanup'){
         echo 'prune and cleanup'
         sh 'npm prune'
         sh 'rm node_modules -rf'
       }
    }
    catch (err) {
        currentBuild.result = "FAILURE"
        throw err
    }
}
