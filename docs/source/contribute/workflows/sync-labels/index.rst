.. _sync-labels-workflow:

Sync Labels
===========

.. dropdown:: Full Workflow
    :animate: fade-in-slide-down

    .. literalinclude:: ../../../../../.github/workflows/sync-labels.yml
        :language: yaml
        :linenos:

What It Does
------------

This workflow synchronizes the repository labels.

.. dropdown:: Labels
    :animate: fade-in-slide-down

    .. literalinclude:: ../../../../../.github/labels.yml
        :language: yaml
        :linenos:

When It Does
------------

.. literalinclude:: ../../../../../.github/workflows/sync-labels.yml
    :language: yaml
    :start-after: name:
    :end-before: concurrency:

This workflow runs whenever there is a push to main in the ``labels.yml`` file.
