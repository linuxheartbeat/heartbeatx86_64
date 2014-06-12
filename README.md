heartbeatx86_64
===============
==========================================================================================  
            STABLE-2.1.4.tar.gz - RPM - BUILD - PROCEDURE
==========================================================================================     

For building heartbeat,stonith,pills RPMS follow the below procedure

1)  Download STABLE-2.1.4.tar.gz tar file from below URL path
    URL: http://hg.linux-ha.org/lha-2.1/archive/STABLE-2.1.4.tar.gz

2)  Create the required directory structure as mentioned below
    # mkdir -p /usr/src/redhat/{BUILD,BUILDROOT,RPMS,SOURCES,SPECS,SRPMS}
    
3)  Keep the STABLE-2.1.4.tar.gz tar file under /usr/src/redhat/SOURCES directory.
    Configure heartbeat-2.1.4 and keep heartbeat.spec file under SPECS directory. And create my own heartbeat-2.1.4.tar.gz tar file
    # cd /usr/src/redhat/SOURCES
    # gtar -zxvf STABLE-2.1.4.tar.gz ; mv Heartbeat-2-1-STABLE-2.1.4 heartbeat-2.1.4
    # cd heartbeat-2.1.4
    # ./ConfigureMe configure --enable-fatal-warnings=no
    # cp heartbeat.spec /usr/src/redhat/SPECS
    # cd /usr/src/redhat/SOURCES    
    # gtar -zcvf heartbeat-2.1.4.tar.gz heartbeat-2.1.4

4)  Now execute the below command to build the heartbeat,stonith,pills RPMS using heartbeat.spec file
    # cd /usr/src/redhat/SPECS
    # rpmbuild -ba heartbeat.spec

5)  Generated heartbeat,stonith,pills RPMS will be available under /usr/src/redhat/RPMS/x86_64/ directory.

==========================================================================================
