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

         mail body: 'project build successful',
                     from: 'support@krazyhawg.com',
                     replyTo: 'noreply@krazyhawg.com',
                     subject: 'project build successful',
                     to: 'bilyeurm@gmail.com'
       }
    }
    catch (err) {

        currentBuild.result = "FAILURE"

            mail body: "project build error is here: ${env.BUILD_URL}" ,
            from: 'build@krazyhawg.com',
            replyTo: 'noreply@krazyhawg.com',
            subject: 'project build failed',
            to: 'bilyeurm@gmail.com'

        throw err
    }
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
A
}
