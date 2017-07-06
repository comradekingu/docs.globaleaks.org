=======================
GlobaLeaks Backup Guide
=======================

The following commands are required in order to create a backup of GlobaLeaks:

date=`date +"%Y-%m-%d"`
version=`dpkg -l | awk '$2=="globaleaks" { print $3 }'`
tar zcvfp /tmp/globaleaks-backup-$date-$version.tar.gz /var/globaleaks/ /etc/default/globaleaks
After the completion of the command you will find inside the temporary directory /tmp/ a tar.gz archive with the name globaleaks-backup-YYYY-MM-DD-XX-YY.ZZ.tar.gz including the archived globaleaks data necessary for backup and restore needs.

If you require to archive permanently the backup proceed saving that backup in your preferred directory.
