========================
Upgrade guide
========================

How to upgrade GlobaLeaks
-------------------------

To safely upgrade a GlobaLeaks installation, please proceed with a backup of your current setup by following the __Backup Guide: https://globaleaks.readthedocs.io/en/latest/BackupGuide.html

This is necessary so that if something goes wrong and you need to roll back, you will be able to just uninstall the current package, then install the same version of GlobaLeaks currently installed.

In order to upgrade GlobaLeaks, perform the following commands:

apt-get update && apt-get install globaleaks
In case of errors

The above commands should allow you to perform regularly updates. Under some conditions due to special updates it could be possible that those commands result in a failure. Consult this page for known specific FAQs on precise failures.

In case you do not find any specific documented solution for your failure, you could run the GlobaLeaks install script again. It is designed to allow upgrading GlobaLeaks and fixing the most common compatibility issues.

To run the install script for updating GlobaLeaks, perform the following command:

"curl https://deb.globaleaks.org/install-globaleaks.sh | bash"
FAQs

Missing or expired PGP key

If your system reports a missing or expired PGP key (W: GPG error: http://deb.globaleaks.org trusty/ Release: The following signatures were invalid: KEYEXPIRED) for the repository be sure to fetch the updated key:

"curl https://deb.globaleaks.org/globaleaks.asc | apt-key add -"

- HTTPS is disabled and I can no longer connect to GlobaLeaks

If you accidentally disabled HTTPS or determined from /var/globaleaks/log/globaleaks.log that the service is no longer serving HTTPS, you may have limited options to connect safely to the platform. If you are running Tor, the platform will be available at its onion address through the Tor browser. If you have specifically removed Tor you may have to proxy your http connections from the application server to re-access the service to repair the configuration.

- GlobaLeaks fails to update due to Tor version incompatibility

If while running "apt-get install globaleaks" in order to update the platform you encounter a Tor version incompatibility, be sure to have added the official Tor repository to your distribution. This requirement has been probably been added after your first setup and to fix the inconvenience and perform you should just run the install script again, so that it will recognize the existing setup, apply the needed fixes and perform the update.

- How do I use the built in HTTPS server instead of Tor2Web?

Version 2.66 of GlobaLeaks introduced HTTPS functionality directly controllable from the administration interface (under Network Settings → HTTPS Settings). In order to migrate an existing installation of GlobaLeaks that uses Tor2Web as the public web proxy you can do the following:

(Note that this guide assumes you can still connect to the service over Tor.)

Update to a version later than 2.66
Add the hostname that will appear on the SSL certificate to Network Settings > Hostname
Disable Network application sandboxing under Network Settings
Stop GlobaLeaks with: "service globaleaks stop"
Remove Tor2Web from the system with: "apt-get remove tor2web"
Start GlobaLeaks with: "service globaleaks start"
Check iptables is disabled with: "iptables --list"
Connect through Tor and upload your private key, certificate, chain file to Network Settings → HTTPS Settings
Click enable in Network Settings → HTTPS Settings
Verify that the service is listening on port 80 with: "netstat -tulpen" If the output does not look like the following:

ubuntu@ip-172-1-0-2:~$ netstat -tulpen
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       User       Inode       PID/Program name
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      0          34391       python               
tcp        0      0 127.0.0.1:9040          0.0.0.0:*               LISTEN      0          31936       tor               
tcp        0      0 0.0.0.0:8082            0.0.0.0:*               LISTEN      0          31592       python                              
tcp        0      0 127.0.0.1:9050          0.0.0.0:*               LISTEN      0          30134       tor          

You may need to add the following line in /etc/default/globaleaks and restart the service.

LISTENING_IP=0.0.0.0

Try to visit the URL displayed in Network Settings → HTTPS Settings with a normal web browser.
If the steps worked, a subprocesses managed by GlobaLeaks should be listening publicly on port 443. You can test the connection against an external service like SSL Labs to verify the quality of the session.
