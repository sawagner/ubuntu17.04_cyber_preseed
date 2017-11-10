lbm-inject for LOUD
---------------------


lbm-inject is a tool for creating installation media used to install LOUD.
This document provides instructions for creating a Docker container
to install and execute lbm-inject.

In order to install the lbm-inject package, the installing machine needs
access to the lcsee internal package repositories, meaning that the machine
hosting the container must be connected to the AER network.



Usage

  - Build a LOUD external Docker container by following the instructions at
      https://webgit.lcseecloud.net/lxerus/lxerus-doc/tree/master/Docker/external


  - Run the container passing the flag granting system-wide root privilege
      > docker run --privileged -v $PATH:/root -i -t loud/lxerus-external
  
      where --privileged is the flag granting root privilege, and $PATH is the path
      to the directory on the host to be mounted inside the container.


  - Change identity to root
      > su -

  
  - Add LOUD internal repositories to sources list

    Create /etc/apt/sources.list.d/lcsee.list
      ## LCSEE Internal
      deb http://mirror.lcsee.wvu.edu/stable/ lxerus-internal/
      deb-src http://mirror.lcsee.wvu.edu/stable/ lxerus-internal/

      ## LCSEE Internal Test
      deb http://mirror.lcsee.wvu.edu/loud/ lxerus-internal-test/
      deb-src http://mirror.lcsee.wvu.edu/loud/ lxerus-internal-test/
    

   - Update package list and install lbm-inject

     > apt-get update
     > apt-get install lbm-inject


   - Done. Ready to execute lbm-inject.  Note that instructions for building
     media for particular machines is stored in Webgit at
       https://webgit.lcseecloud.net/lxerus/lxerus-doc/tree/master/INSTALL






 -- Terry Ferrett <terry.ferrett@mail.wvu.edu>, Mon, 16 May 2016 00:47:21 -0700
