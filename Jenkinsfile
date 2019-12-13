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
  -Dsonar.host.url=http://3.90.60.137/:9000 \
  -Dsonar.loginapp=abaac7da3ff231f253b0655eeb25ba85d4969b28  ")

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
