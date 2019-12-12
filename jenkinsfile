  node{
    stage('scm checkout'){
        git 'https://github.com/Sravan-Aws/Login-nexus.git'
    }
     stage('clean'){
    
def MVN_HOME = tool name: 'MVN_HOME', type: 'maven'

def mvn = "${MVN_HOME}/bin/mvn"

echo "mvn=$mvn"

sh("${mvn} clean ")

}
    stage('code scan'){
    
def MVN_HOME = tool name: 'MVN_HOME', type: 'maven'

def mvn = "${MVN_HOME}/bin/mvn"

echo "mvn=$mvn"

sh("${mvn}  sonar:sonar \
  -Dsonar.host.url=http://52.206.87.176:9000 \
  -Dsonar.loginapp=2d52bb44431a113b02c4cb1a288b0371caa3238e  ")

}
stage('package'){
    
def MVN_HOME = tool name: 'MVN_HOME', type: 'maven'

def mvn = "${MVN_HOME}/bin/mvn"

echo "mvn=$mvn"

sh("${mvn} package ")

}
stage('deploy'){
    
def MVN_HOME = tool name: 'MVN_HOME', type: 'maven'

def mvn = "${MVN_HOME}/bin/mvn"

echo "mvn=$mvn"

sh("${mvn} deploy ")




}}
