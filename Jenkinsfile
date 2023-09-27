//Declarative Pipeline 
pipeline{
tools{
jdk 'myjdk'
maven 'mymvn'
}
agent any
stages{
stage('Clone Repo')
{
steps{
git 'https://github.com/adebayoadebusoye1/DevOps_Djatl1.git'
}
}
stage('Compile on Slave1')
{
agent{label 'slave1'}
steps{
sh 'mvn compile'
}
}
stage('Code Analysis on Slave2')
{
agent{label 'slave2'}
steps{
sh 'mvn pmd:pmd'
}
}
stage('Build the artifact on Master')
{
agent any
steps{
sh 'mvn package'
}
}
}
}
