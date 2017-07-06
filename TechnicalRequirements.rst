======================
Technical Requirements
======================

Make sure you understand and satisfy each of these technical requirements:

**Operating System**
--------------------
GlobaLeaks is designed to run on Linux and Ubuntu Xenial 16.04 LTS is the officially supported platform.
Support for more distributions is planned.

**Server sizing**
-----------------
For security and resource availability, GlobaLeaks needs a dedicated server. Depending on the Architecture you may need one or two servers to be allocated to GlobaLeaks. The two-server architecture requires that you use different data-centres for hosting each of them.

**Minimum requirements**:

- CPU : Dual core 2.0gHz
- RAM : 4GB (Does not impact the maximum file size that a node can handle in upload)
- STORAGE: 40GB Allocate more based on data retention policy and (expected) traffic.
- I/O : 10Mbit/s (shared)
- Email account

GlobaLeaks makes use of email to handle tip notification. To this aim you need an email account to be used to send Tip related notifications to the recipients. This e-mail account needs to be available and the respective SMTP server must support SMTPS or SMTP/TLS in order to securely manage sending of e-mail.

**Linux skills**
----------------
To setup and maintain GlobaLeaks you should have basic Linux skills, practice in installing packages, upgrading, running web servers, basic debugging and analysis of email logs.

