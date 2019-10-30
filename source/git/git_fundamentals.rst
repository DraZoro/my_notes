================
Git Fundamentals
================

Support packages for building Git
---------------------------------

.. code:: bash 

   # RPM system 
   yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel
   # Debian system 
   apt-get install libcurl4-gnutils-dev libexpat1-dev gettext libz-dev \
   libssl-dev

The source code can be found from `Kernel.org`_ or `Github Repo`_ sites.


Global Configuration 
--------------------

.. code:: console

   # File : ~/.gitconfig 
   [user]
      name = Clement Thulani Mahlangu
      email = clement.mahlangu@gmail.com
   [color]
      ui = auto
   [alias]
      st = status 
      co = checkout 
      br = branch 
      up = rebase 
      ci = commit 
   [core]
      editor = /usr/bin/vim
      exclude = /home/drazoro/.gitignore_global
   [push]
      default = matching 

.. External links
.. _Kernel.org: http://www.kernel.org/pub/software/scm/git
.. _Github Repo: https://github.com/git/git/releases
