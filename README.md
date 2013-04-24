Deploy OpenMEAP on Tomcat 7 (JBoss EWS 2.0) using OpenShift
============================

This git repository helps you get up and running quickly w/ an OpenMEAP installation on Tomcat 7 (JBoss EWS 2.0) using OpenShift.

Steps to get OpenMEAP deployed to Tomcat 7 (JBoss EWS 2.0) running on OpenShift
----------------------------

Create an account at http://openshift.redhat.com/ , don't forget to create a namespace and install client tools as well.

Install the client tools on your machine if you have not already done so.

	sudo gem install rhc

Create the application

    rhc app create -a openmeap -t jbossews-2.0

Navigate to the openmeap directory and as we are using an exploded war deployment so we will delete “pom.xml”

	git rm -rf src/ pom.xml
	commit -a -m 'removing default files'

Download the war files from from these URL's and copy the war file in openmeap/webapps directory	
	
	https://github.com/OpenMEAP/openshift-openmeap-quickstart/blob/master/webapps/openmeap-admin-web.war
	https://github.com/OpenMEAP/openshift-openmeap-quickstart/blob/master/webapps/openmeap-services-web.war
	https://github.com/OpenMEAP/openshift-openmeap-quickstart/blob/master/webapps/banking-web.war
	https://github.com/OpenMEAP/openshift-openmeap-quickstart/blob/master/webapps/test.war.dodeploy
	
Add the OpenMEAP WAR files

	git add webapps/openmeap-admin-web.war
	git add webapps/openmeap-services-web.war
	git add webapps/banking-web.war
	git add webapps/test.war.dodeploy
	git commit -a -m 'adding war files'

Get Tomcat 7 (JBoss EWS 2.0) running OpenMEAP
----------------------------

Pushing the code to OpenShift

	git push

That's it, you can now checkout your OpenMEAP install at:

    https://openmeap-$yournamespace.rhcloud.com/openmeap-admin-web/interface/

The default managing account is openmeap/openshift

With latest cartridges, you should be able to use thee commands to restart server or app if you need to.

ctl_all restart ctl_app restart