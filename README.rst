======================
My summaries and notes
======================

Summary
-------

This is used to keep my notes in one place. `Sphinx`_ is used to build the
documentation.

Building the documentation steps.

1. Cloning and installation the packages. 

   .. code:: bash 

      git clone https://github.com/DraZoro/my_notes.git
      cd my_notes
      python3 -m pip install --user --upgrade pip
      python3 -m pip install --user virtualenv
      python3 -m venv env
      source env/bin/activate
      pip install -r requirements.txt

2. Manually building the documents, this example is for html. 

   .. code:: bash

      make html 

3. To do explore the use of `sphinx-autobuild` environment. 

   .. code:: bash

      sphinx-autobuild . _build_html


.. Web sites
.. _Sphinx: http://sphinx-doc.org
.. _virtualenvwrapper: http://virtualenvwrapper.readthedocs.io/en/latest/index.html