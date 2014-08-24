CloudFormation template for create puppet master (ubuntu) and agent (windows)
==================
This repo is hosting template files for creating puppet master and agent on aws. Puppet Master is using ubuntu, and puppet agent is using windows server 2012.

### How to use
Clone this repo:
	
	git clone 
	cd 
		
##### For puppet master

	aws cloudformation create-stack \
    	--stack-name puppet-master-$( date +%s ) \
	    --template-body "$( cat master-template.json )" \
	   	--parameters "$(cat master-parameters.json)" \
	    --capabilities CAPABILITY_IAM
	    
##### For puppet agent

	aws cloudformation create-stack \
	    --stack-name puppet-agent-$( date +%s ) \
    	--template-body "$( cat agent-template.json )" \
	   	--parameters "$(cat agent-parameters.json)" \
	    --capabilities CAPABILITY_IAM

##### For puppet master with default modules	    
If you want to create a puppet master with default modules please use another master template, before create it you need edit `master-parameter.json` set to **ModuleTarLocation** to point to your modules tarball url. Please be sure you tarball shoule be following file structure.

```
modules
	┣━━hellow-world
	┣━━hellow-world-1
	┣━━hellow-world-2
	┗━━hellow-world-3			    
```
Create master with following command

	aws cloudformation create-stack \
    	--stack-name puppet-master-$( date +%s ) \
	    --template-body "$( cat master-with-default-modules-template.json )" \
	   	--parameters "$(cat master-parameters.json)" \
	    --capabilities CAPABILITY_IAM


