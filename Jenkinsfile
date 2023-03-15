pipeline{
    agent any
    tools {
}
// stages{
//         stage('creds test'){
//             steps{
//                 withCredentials([file(credentialsId: 'gcp-auth-jenkins', variable: '')]) {
//    // some block
// }
//             }
//         }
        stage('Git Checkout'){
            steps{
                git branch: 'master', credentialsId: '0093fc89-b721-4ff0-8311-3e369d1e56fc', url: 'https://github.com/sirisha423/wordpress.git'
            }
        }
  stage('Build WordPress') {
            steps {
                // sh 'npm install'
                // sh 'npm run build'
                sh 'tar cvf wordpress.tar .'
            }
        }
        stage('Upload to Cloud Storage') {
            steps {
//                 withCredentials([googleServiceAccount(credentialsId: 'gcp-creds', scope: ['https://www.googleapis.com/auth/cloud-platform'])]) {
                    sh "gsutil cp -r wordpress.tar gs://your-bucket-name/wordpress.tar"
                }
            }
        }
