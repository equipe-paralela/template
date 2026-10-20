Architecture
============

Each tool handles one stage, from extracting information out of the source code to publishing the result online.

#. **Doxygen** creates XML files from the C C source code.
#. **Breathe** generates RST files from the Doxygen-generated XML files.
#. **Exhale** links the RST files from the Breathe-generated RST files.
#. **Sphinx** builds the HTML from the ``.rst`` files.
#. **Read the Docs** publishes the documentation online automatically.

.. note::
    **Doxygen**, **Breathe** and **Exhale** are only used in repositories that contain C source code.

Each page is a file named ``index.rst`` inside its own folder (``docs/section/index.rst``). This structure makes it easy to move pages to another location and keeps the URLs clean (``/section/``), while keeping one file equal to one page on the website.
