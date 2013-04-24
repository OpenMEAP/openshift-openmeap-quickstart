OpenMEAP on Tomcat 7 (JBoss EWS 2.0) using OpenShift
============================

This git repository helps you get up and running quickly w/ an OpenMEAP installation on Tomcat 7 (JBoss EWS 2.0) using OpenShift.

Steps to get OpenMEAP deployed on OpenShift.
----------------------------

Create an account at http://openshift.redhat.com/ , don't forget to create a namespace and install client tools as well.

Install the client tools on your machine if you have not already done so.

	sudo gem install rhc

Create the application.

    rhc app create -a openmeap -t jbossews-2.0

Navigate to the openmeap directory and as we are using an exploded war deployment, we will delete “pom.xml”

	git rm -rf src/ pom.xml
	git commit -a -m 'removing default files'
	
Grab this quickstart code and to get Tomcat 7 (JBoss EWS 2.0) running OpenMEAP.
	
	git remote add upstream -m master git://github.com/OpenMEAP/openshift-openmeap-quickstart
	git pull -s recursive -X theirs upstream master
	
Push the code to OpenShift.

	git push

That's it, you can now checkout your OpenMEAP install at:

    https://openmeap-$yournamespace.rhcloud.com/openmeap-admin-web/interface/

The default managing account. 

	openshift/openmeap

Once logged in, change your Global Settings & Cluster Nodes. 

	External Service Url: https://$yournamespace/openmeap-services-web
	Max File Upload Size: 100000000
	File-system Storage Path Prefix: /var/lib/openshift/Syourhomedirname/app-root/data
	
	Admin Server Accessible Service Url: https://$yournamespace/openmeap-services-web
	File-system Storage Path Prefix: /var/lib/openshift/Syourhomedirname/app-root/data
