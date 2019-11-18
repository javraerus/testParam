import jenkins.* 
import jenkins.model.* 
import hudson.* 
import hudson.model.*


name = "dse-na/jraezrus/testtt" 
def itemx = Jenkins.instance.getItemByFullName(name) 
def namestr = itemx.getFullDisplayName() 
println "item name is: <" + namestr + ">"

def listaparameterDefinitions = []

def environment1 = new StringParameterDefinition("environment1","Yes"); 
def environment2 = new StringParameterDefinition("environment2","Yes"); 
def environment3 = new StringParameterDefinition("environment3","No"); 
def environment4 = new StringParameterDefinition("environment4","0.0.1-SNAPSHOT"); 
def flag = new StringParameterDefinition("flag","OFF");

listaparameterDefinitions.add(environment1);

listaparameterDefinitions.add(environment2); 
listaparameterDefinitions.add(environment3); 
listaparameterDefinitions.add(environment4); 
listaparameterDefinitions.add(flag);

/* 
def listaparameterDefinitions = [ 
new StringParameterDefinition("environment1","Yes"), 
new StringParameterDefinition("environment2","Yes"), 
new StringParameterDefinition("environment3","No"), 
new StringParameterDefinition("environment4","0.0.1-SNAPSHOT"), 
new StringParameterDefinition("flag","OFF") kjh gkhj gkjh gkjh gkjh
] 
*/

def parameter=new ParametersDefinitionProperty(listaparameterDefinitions); 

itemx.addProperty(parameter); 
 

node () {
 checkout scm
    stage('Print env vars') {

    build job: 'testtt', parameters: [[$class: 'StringParameterValue', name: 'environment1', value: "Yes"], [$class: 'StringParameterValue', name: 'environment2', value: "Yes"], [$class: 'StringParameterValue', name: 'environment3', value: "Up"],[$class: 'StringParameterValue', name: 'environment4', value: "1.0.3-SNAPSHOT"],[$class: 'StringParameterValue', name: 'flag', value: "OFF"]]

    }

} 

