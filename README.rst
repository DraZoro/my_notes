======================
My summaries and notes
======================

Summary
-------

This is used to keep my notes in one place. `Sphinx`_ is used to build the
documentation.

Building the documentation steps.

1. I make use of `Pyenv`_ for managing Python version together with 
   `Pyenv-virtualenv`_ and `Pipenv`_ for managing  dependancies.

   .. code:: bash 

      pyenv install 3.8.0 
      pyenv virtualenv 3.8.0 sphinx 
      pyenv activate sphinx 


3. Run the `sphinx-autobuild` environment. It will give the localhost URL.

   .. code:: bash

      sphinx-autobuild . _build_html


.. Web sites
.. _Sphinx: http://sphinx-doc.org
.. _Pyenv: https://github.com/pyenv/pyenv
.. _Pyenv-virtualenv: https://github.com/pyenv/pyenv-virtualenv
.. _Pipenv: https://github.com/pypa/pipenv
.. _virtualenvwrapper: http://virtualenvwrapper.readthedocs.io/en/latest/index.html
