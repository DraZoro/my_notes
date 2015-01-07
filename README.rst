======================
My summaries and notes
======================

|build-status| |docs|

Summary
-------

This is used to keep my notes in one place. `Sphinx`_ is used to build the
documentation. 

Building the documentation steps.

.. code:: bash 

   sudo pip install sphinx 
   sudo pip install sphinx-autobuild 
   # Then within the root of the documentation run
   sphinx-autobuild . _build_html

.. Web sites
.. _Sphinx: http://sphinx-doc.org

.. |build-status| image:: https://img.shields.io/travis/rtfd/readthedocs.org.svg?style=flat    
    :alt: build status    
    :scale: 100%    
    :target: https://travis-ci.org/rtfd/readthedocs.org

..  |docs| image:: https://readthedocs.org/projects/docs/badge/?version=latest    
     :alt: Documentation Status    
     :scale: 100%    
     :target: https://readthedocs.org/projects/docs/

