OpenMEAP on Tomcat 7 (JBoss EWS 2.0) using OpenShift
============================

This git repository helps you get up and running quickly w/ an OpenMEAP installation on Tomcat 7 (JBoss EWS 2.0) using OpenShift.

Steps to get OpenMEAP deployed on OpenShift.
----------------------------

Create an account at http://openshift.redhat.com/ , don't forget to create a namespace and install Git, Ruby and the client tools if needed.

Install the client tools on your machine if you have not already done so.

	sudo gem install rhc

Create the application.

    rhc app create -a openmeap -t jbossews-2.0 --from-code git://github.com/OpenMEAP/openshift-openmeap-quickstart

Start the server on OpenShift.

	rhc app restart -a openmeap

That's it, you can now checkout your OpenMEAP install at:

    https://openmeap-$yournamespace.rhcloud.com/openmeap-admin-web/interface/

The default managing account. 

	openshift/openmeap

Once logged in, update Global Settings & Cluster Nodes. 

	Change yournamespace in both Service Urls: https://openmeap-$yournamespace.rhcloud.com/openmeap-services-web
    Save Settings

Building the mobile clients.
----------------------------

	Use: openmeap.slic.appMgmtServiceUrl=https://openmeap-$yournamespace.rhcloud.com/openmeap-services-web/application-management 
	
	See wiki.openmeap.com for building the SLIC clients.

	
