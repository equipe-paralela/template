Development
===========

The workflow to be follow when suggesting modifications designed with `Mermaid <https://mermaid.js.org/intro/>`_ is:

.. mermaid::
    :align: center
    :caption: Development Strategy
    :zoom:

    ---
    config:
    flowchart:
        curve: basis
    ---
    flowchart TB
        classDef local  fill:#003300,stroke:#888,stroke-width:1px,color:#fff
        classDef remote fill:#000033,stroke:#888,stroke-width:1px,color:#fff

        A((open<br>Issue)):::remote
        B1[create<br>Branch]:::local
        B2[sync<br>with main]:::local
        C1[add<br>modifications]:::local
        C2[add<br>validation]:::local
        C3[add<br>documentation]:::local
        D1[push<br>Branch]:::local
        Q{PR<br>exists?}:::remote
        E[create<br>Pull Request]:::remote
        F[workflows<br>pass?]:::remote
        G[review<br>accepted?]:::remote
        H([merge<br>Pull Request]):::remote
        I[clean up<br>branches]:::local

        B1 ~~~ B2
        A ==> B1
        B1 ==> C1
        B2 ==> C1
        C1 ==> C2
        C2 ==> C3
        C3 ==> D1
        D1 ==> Q
        Q -->|no| E
        Q ==>|yes| F
        E --> F
        F ==>|yes| G
        F -->|no| B2
        G ==>|yes| H
        G -->|no| B2
        H ==> I

.. raw:: html

    <p>With local side operations in <span style="color:#77ff77"><b>green</b></span> and remote side operations in <span style="color:#7777ff"><b>blue</b></span>.</p>

Branches
--------

Naming
^^^^^^

Each branch name **should** respect the following naming structure:

.. code-block:: text

    <type>/<description>

With the same accepted types as those for the :ref:`commit-messages` and the description words separated by ``-``.

.. _commit-messages:

Commits
-------

Messages
^^^^^^^^

Each commit message **must** respect the `conventional commits <https://www.conventionalcommits.org/en/v1.0.0/>`_ structure to ensure releases created by `semantic-release <https://github.com/semantic-release/semantic-release>`_ follow the `semantic versioning <https://semver.org/>`_ convention. Therefore the following commit message structure is required:

.. code-block:: text

    <type>[optional scope]: <description>

    [optional body]

    [optional footer(s)]

.. dropdown:: Accepted Types
    :animate: fade-in-slide-down
    :open:

    Based on `Angular <https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines>`_ commit guidelines:

    ============ =================================================================
    Types        Application
    ============ =================================================================
    ``build``    modifications affecting the build system or external dependencies
    ``ci``       modifications affecting CI configuration files and scripts
    ``docs``     modifications only on documentation
    ``feat``     addition of a new feature
    ``fix``      correction of a bug
    ``perf``     modifications bringing performance improvements
    ``refactor`` modifications that neither fixes a bug nor adds a feature
    ``style``    modifications not affecting code behavior
    ``test``     addition or correction of tests
    ============ =================================================================

.. note::
    Breaking API change commit message must include either:

    - a footer ``BREAKING CHANGE:``
    - a ``!`` after the type/scope

    Adapted from the `conventional commits specification <https://www.conventionalcommits.org/en/v1.0.0/#specification>`_.

.. tip::
    **Read** the `conventional commits specification <https://www.conventionalcommits.org/en/v1.0.0/#specification>`_ for details on the do's and dont's.

Issues
------

Labels
^^^^^^

At least one of the following accepted labels **must** be included:

.. dropdown:: Accepted Labels
    :animate: fade-in-slide-down
    :open:

    .. literalinclude:: ../../../../.github/labels.yml
        :language: yaml
        :linenos:

.. tip::
    Labels are automatically synchronized in the repository by the :ref:`sync-labels-workflow` workflow if this convention is followed.

Types
^^^^^

Each modification **must** be described on an Issue using either a Bug or a Feature Issue template as described:

.. dropdown:: Bug Issue
    :animate: fade-in-slide-down

    .. literalinclude:: ../../../../.github/ISSUE_TEMPLATE/bug.md
        :language: markdown
        :linenos:

.. dropdown:: Feature Issue
    :animate: fade-in-slide-down

    .. literalinclude:: ../../../../.github/ISSUE_TEMPLATE/feature.md
        :language: markdown
        :linenos:

Pull Requests Creation
----------------------

Each working branch should be linked to a single Pull Request where it's title **must** respect the :ref:`commit-messages` structure. When merging, the squash approach is used and the title will be used as default commit message.

..  warning::
    A Pull Request will be accepted if, and only if, the naming structure is respected and pass the `cicd.yml <.github/workflows/cicd.yml>`_ workflow.

    If disrespected, `semantic-release <https://github.com/semantic-release/semantic-release>`_ will disconsider the Pull Request and incorrectly determine the next release version.

.. tip::
    Labels are automatically added by the :ref:`pull-request-workflow` workflow if this convention is followed.
