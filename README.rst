===========================================
RaspMate
===========================================

Raspberry Pi Automation Center Project
===============

Install WebIOPi
  $ wget http://downloads.sourceforge.net/project/webiopi/WebIOPi-0.7.1.tar.gz
  $ tar xvzf WebIOPi-x.y.z.tar.gz
  $ cd WebIOPi-x.y.z
  $ ./setup.sh

Change Password
  $ webiopi-passwd

Start on boot
  $ update-rc.d webiopi defaults

Don't start apache on boot
  $ update-rc.d apache2 remove

Start WebIOPi on verbose mode
  $ webiopi -c /etc/webiopi/config
( Use " -l /etc/webiopi/webiopi.log" to create a log file )
Start|Stop on background
  $ /etc/init.d/webiopi start|stop|restart

