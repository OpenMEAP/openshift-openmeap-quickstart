Deploy OpenMEAP on Tomcat using OpenShift
============================

This git repository helps you get up and running quickly w/ a OpenMEAP installation on Tomcat using OpenShift.

Create a DIY app on OpenShift
----------------------------

Create an account at http://openshift.redhat.com/ , don't forget to create a namespace and install client tools as well.

Create a DIY application

    rhc app create -a openmeap -t diy-0.1

Get Tomcat running
----------------------------
Grab this quickstart codes and make it working for you!

    cd openmeap
    git remote add upstream -m master git://github.com/OpenMEAP/openshift-openmeap-quickstart
    git pull -s recursive -X theirs upstream master
    git push

That's it, you can now checkout your tomcat at:

    http://tomcat-$yournamespace.rhcloud.com

The default managing account is openmeap/openshift

License
-------

This code is dedicated to the public domain to the maximum extent
permitted by applicable law, pursuant to CC0
http://creativecommons.org/publicdomain/zero/1.0/
