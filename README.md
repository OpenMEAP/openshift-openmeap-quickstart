Deploy OpenMEAP on Tomcat using OpenShift
============================

This git repository helps you get up and running quickly w/ an OpenMEAP installation on Tomcat7 using OpenShift.

Steps to get OpenMEAP deployed to Tomcat7 running on OpenShift
----------------------------

Create an account at http://openshift.redhat.com/ , don't forget to create a namespace and install client tools as well.

Create the application

    rhc app create -a openmeap -t diy-0.1

Get Tomcat running OpenMEAP
----------------------------
Grab this quickstart codes and make it working for you!

    cd openmeap
    git remote add upstream -m master git://github.com/OpenMEAP/openshift-openmeap-quickstart
    git pull -s recursive -X theirs upstream master
    git push

That's it, you can now checkout your tomcat at:

    http://openmeap-$yournamespace.rhcloud.com


Deploy the OpenMEAP war files through the Tomcat Manager and add user roles to tomcat users.mxl