pipeline{
agent any

stages {
 stage ('build'){
input{
  message "please specify environment:"
  ok "ok"
  submitter "user1,admin@gmail.com"
  submitterParameter "who is submitter"
                   parameters{
                      string(name: 'environment', defaultValue: 'dev', description: 'environment to build for (valid values: dev, test, prod)')
                      string(name: 'version', defaultValue: '1.0', description: 'version number to build for')
     booleanParam(name: 'to_deply_to_environment', defaultValue: true, description:'')
choice(choice: 'US-EAST-1\nUS-WEST-2', description: 'what aws region?', name: 'region')
text(name: 'myText', defaultValue: 'mytext value', description:'mytext')
password(name: 'mypassoword', defaultValue: 'mypaswordvalue', description:'mydescription')
file(name: 'myfile', description: 'filedescription')
credentials(name:'mycredentials', description:'mycredentialsDesc', reuired:true)
}
   }
steps{
echo "we are building for ${environment}, ${version}, and we are deploying to environment: ${to_deploy_to_environment}"
echo "region:${region}, mytext: ${mytext}, mypassword: ${mypassword}, and my file: ${myfile}"
echo "submitter is: ${whoissubmitter}"
echo "selected credentials is: ${mycredentials}"
}
}
 }
}
