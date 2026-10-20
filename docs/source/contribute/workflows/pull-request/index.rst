.. _pull-request-workflow:

Pull Request
============

.. dropdown:: Full Workflow
    :animate: fade-in-slide-down

    .. literalinclude:: ../../../../../.github/workflows/pull-request.yml
        :language: yaml
        :linenos:

What It Does
------------

This workflow verifies if Pull Request name respects the required structure and adds labels based on the branch name and files modified.

..  tip::
    If no label is added, a comment suggesting labels will be added.

When It Does
------------

.. literalinclude:: ../../../../../.github/workflows/pull-request.yml
    :language: yaml
    :start-after: name:
    :end-before: concurrency:

This workflow runs whenever a pull request is edited, opened or synchronized.
