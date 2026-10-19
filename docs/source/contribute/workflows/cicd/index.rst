.. _cicd-workflow:

CI/CD
=====

.. dropdown:: Full Workflow
    :animate: fade-in-slide-down

    .. literalinclude:: ../../../../../.github/workflows/cicd.yml
        :language: yaml
        :linenos:

What It Does
------------

This workflow verifies if Pull Request :ref:`commit-messages` and Name respects the required structure and adds labels based on the it's contents.

..  tip::
    If no label is added, a comment suggesting labels will be added.

When It Does
------------

.. literalinclude:: ../../../../../.github/workflows/cicd.yml
    :language: yaml
    :start-after: name:
    :end-before: permissions:

This workflow runs whenever a pull request is altered.
