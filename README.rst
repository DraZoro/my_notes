======================
My summaries and notes
======================

Summary
-------

This is used to keep my notes in one place. `Sphinx`_ is used to build the
documentation.

Building the documentation steps.

1. Make the virtual environment using `virtualenvwrapper`_.

   .. code:: bash

      mkvirtualenv -p /usr/bin/python2.7 sphinx

2. Install the requirements.

   .. code:: bash

      pip2 install -r requirements.txt

3. Run the `sphinx-autobuild` environment. It will give the localhost URL.

   .. code:: bash

      sphinx-autobuild . _build_html


.. Web sites
.. _Sphinx: http://sphinx-doc.org
.. _virtualenvwrapper: http://virtualenvwrapper.readthedocs.io/en/latest/index.html
