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

Once logged in, change your Global Settings & Cluster Nodes. 

	External Service Url: https://openmeap-$yournamespace.rhcloud.com/openmeap-services-web
	Max File Upload Size: 100000000
	File-system Storage Path Prefix: app-root/data
	
	Admin Server Accessible Service Url: https://openmeap-$yournamespace.rhcloud.com/openmeap-services-web
	File-system Storage Path Prefix: app-root/data

Click Add Application.

	Name: OpenMEAP
	Initial Version Identifier: 0.0.1a
	See wiki.openmeap.com for users, groups and permissions

Download OpenShift Mobile Application.

	URL: http://www.openmeap.com/wp-content/uploads/apps/openshift.zip

Click Applications and add a version.

	Identifier: OpenShift
	Upload: openshift.zip 
	Submit

Building the mobile clients.
----------------------------

	Use: openmeap.slic.appMgmtServiceUrl=https://openmeap-$yournamespace.rhcloud.com/openmeap-services-web/application-management 
	
	See wiki.openmeap.com for building the SLIC clients.

	
