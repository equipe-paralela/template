Usage
=====

.. note::

   First follow the :ref:`docs-installation` instructions.

Clean the previous build, run Doxygen with the ``Doxyfile`` configuration, and build the HTML documentation with Sphinx:

.. code-block:: bash

   make clean
   doxygen Doxyfile
   make html

.. tip::

   The following command is a shortcut for the previous series of commands:

   .. code-block:: bash

      make docs

Then open the ``docs/build/html/index.html`` file in a browser to evaluate the changes before pushing to the remote.

Pull Request
------------

Every commit to a Pull Request triggers Read the Docs, and a preview of the changes is displayed online. The preview should be evaluated before approving the Pull Request.

Learning reStructuredText
-------------------------

Anyone who is not familiar with the RST syntax can learn how to write the documentation from the following sources:

* `reStructuredText Sphinx <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`__: an introduction to the syntax as used by Sphinx.
* `reStructuredText Docutils <https://docutils.sourceforge.io/docs/user/rst/quickref.html>`__:
  a quick reference of the markup.
* `Sphinx Directives <https://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html>`__: reference for directives such as ``note``, ``tip`` and ``code-block``.
* `Sphinx Roles <https://www.sphinx-doc.org/en/master/usage/restructuredtext/roles.html>`__: reference for roles such as ``:ref:``.
