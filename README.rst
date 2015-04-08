===========================================
RaspMate
===========================================

Raspberry Pi Automation Center Project
===============

Install WebIOPi;

  $ wget http://downloads.sourceforge.net/project/webiopi/WebIOPi-0.7.1.tar.gz
  
  $ tar xvzf WebIOPi-x.y.z.tar.gz
  
  $ cd WebIOPi-x.y.z
  
  $ ./setup.sh

Change Password;

  $ webiopi-passwd

Start on boot;

  $ update-rc.d webiopi defaults

Don't start apache on boot;

  $ update-rc.d apache2 remove

Start WebIOPi on verbose mode. Use " -l /etc/webiopi/webiopi.log" to create a log file;

  $ webiopi -c /etc/webiopi/config

Start|Stop on background;

  $ /etc/init.d/webiopi start|stop|restart
  
Install Samba;

  $ apt-get install samba
  
Edit /etc/samba/smb.conf;
  
  [global]
  
  security = user
  
  guest account = nobody
  
  map to guest = bad password
  
  
  [RaspMate]
  
  comment=RaspMate Folders
  
  browseable=yes
  
  path=/usr/share/webiopi
  
  public=yes
  
  writable=yes
  
  guest ok=yes
  
  read only=no
  
  create mask = 0777
  
  directory mask = 0777
  
Start Samba;

  $ update-rc.d samba defaults
  
  $ service samba start
  
Install Localepurge;

  $ apt-get install localepurge 
  
Install deborphan;

  $ apt-get install deborphan 
  
Clean and purge unused locales and orphans;

  $ localepurge
  
  $ apt-get remove --purge `deborphan --guess-all`
  
  $ apt-get clean
  
