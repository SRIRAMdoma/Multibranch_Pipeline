pipeline{
agent any
stages{
stage('check_out'){
steps{
git credentialsId: '6600219a-4d57-46b5-b20b-4e035844d072', url: 'https://github.com/venkybabu99/Multibranch_Pipeline.git'
stage('Hello world'){
steps{
echo "**********Multibrach pipeline*************"
}
}
}
}