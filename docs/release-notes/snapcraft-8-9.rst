.. _release-8.9:

Snapcraft 8.9 release notes
===========================

12 May 2025

Learn about the new features, changes, and fixes introduced in Snapcraft 8.9.

Requirements and compatibility
------------------------------

See :ref:`reference-system-requirements` for information on the minimum hardware and
installed software.

What's new
----------

Snapcraft 8.9 brings the following features, integrations, and improvements.

Test command
~~~~~~~~~~~~

A new command called ``test``, and its accompanying ``init`` profile, are available for
testing snaps. They leverage `Spread`_ to run tests identically on local and remote
systems.

The command is experimental and subject to change. To try it on an existing snap
project, run ``snapcraft init --profile=test`` at the root of your project directory.
For a description of the command and its options, see the :ref:`test command
<ref_commands_test>` reference.

Cargo use plugin
~~~~~~~~~~~~~~~~

We added a plugin that sets up a local `cargo registry`_ for `Rust crates`_. These
crates can then be used by the existing :ref:`Rust plugin <craft_parts_rust_plugin>`.
See the :ref:`craft_parts_cargo_use_plugin` reference for details.

Gradle plugin
~~~~~~~~~~~~~

Previously, Snapcraft supported the `Gradle`_ build tool for core18 snaps.

Support for Gradle is now available for core22 and core24 snaps with a new Gradle
plugin. See the :ref:`craft_parts_gradle_plugin` reference for details.

Documentation migration and redesign
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Previously, the main source of Snapcraft documentation was hosted on a Discourse
instance at `snapcraft.io <http://snapcraft.io/docs>`_.

With Snapcraft 8.9, the essential documentation was shifted to ReadTheDocs and is now
hosted inside the Snapcraft repository. In the process, much of the documentation was
reorganized and rewritten to closely follow the `Diátaxis framework
<https://diataxis.fr>`_.

The documentation now aligns more closely with the learning experience of all Canonical
products. It's also versioned with each Snapcraft release.

We're working to retire the remaining documentation on snapcraft.io.


New documentation domain
~~~~~~~~~~~~~~~~~~~~~~~~

The second Snapcraft documentation set -- the one you're reading now -- was first
deployed to the ReadTheDocs domain.

Snapcraft is an important member of the Canonical community and ecosystem, and all its
site names should demonstrate that. With this release, we gave the docs a new home at
the Ubuntu domain. You can now reach it at:

`documentation.ubuntu.com/snapcraft <https://documentation.ubuntu.com/snapcraft>`_

We put redirects in place to handle links to the old ReadTheDocs domain.

With this change, we also removed the language subdirectory (``/en``) in the URL, to
shave a few characters off all links.


Corrections to build provider documentation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We've corrected several parts of the :ref:`tutorial <tutorial-craft-a-snap>` and
:ref:`Set up Snapcraft <how-to-set-up-snapcraft>` related to installing Snapcraft and
setting up LXD. The instructions are now up-to-date.


Minor features
--------------

Snapcraft 8.9 brings the following minor changes.

Support for Maven wrappers
~~~~~~~~~~~~~~~~~~~~~~~~~~

The Maven plugin now supports the ``maven-use-wrapper`` key to indicate that the build
should use the wrapper provided by the source code. See the
:ref:`craft_parts_maven_plugin` reference for details.

Backwards-incompatible changes
------------------------------

The following changes are incompatible with previous versions of Snapcraft.

Renaming of confdb schema commands
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A `confdb schema <https://snapcraft.io/docs/configure-with-confdb>`_ defines the
configuration of Linux systems, including storage, access permission, granularity,
and sharing between snaps.

The existing confdb schema commands have been renamed as follows:

.. list-table::
    :header-rows: 1

    * - Old command
      - New command
    * - ``list-confdbs``
      - ``list-confdb-schemas``
    * - ``edit-confdbs``
      - ``edit-confdb-schema``

Known issues
------------

The following issues were reported and are scheduled to be fixed in upcoming
patch releases.

See individual issue links for any mitigations.

- `#5272`_ The GNOME extension sets the wrong ``CMAKE_PREFIX_PATH``.

Fixed bugs and issues
---------------------

The following issues have been resolved in Snapcraft 8.9.

Snapcraft 8.9.0
~~~~~~~~~~~~~~~

- `#5107`_ Plugin errors would provide broken links to documentation.

Snapcraft 8.9.1
~~~~~~~~~~~~~~~

- The uv plugin was breaking with uv 0.7.
- The ``snapcraft test`` command would fail to install snaps with devmode confinement.

Snapcraft 8.9.2
~~~~~~~~~~~~~~~

- YAML issues originating from the project file now emit errors instead of tracebacks,
  making them easier to identify and read.
- `#5491`_ Project variables weren't being evaluated in project files.

Snapcraft 8.9.3
~~~~~~~~~~~~~~~

- `#5522`_ Minimum Python version changed to 3.10.

Snapcraft 8.9.4
~~~~~~~~~~~~~~~

- Addressed all snapcraft.io/docs links in the code and docs.
- Retired legacy Ruby how-to guide.
- Corrected the values in the description of the ``confinement`` key.

Snapcraft 8.9.5
~~~~~~~~~~~~~~~

- Updated all part keys in the :ref:`snapcraft.yaml reference
  <reference-snapcraft-yaml-part-keys>`.

Contributors
------------

We would like to express a big thank you to all the people who contributed to
this release.

:literalref:`@astrojuanlu<https://github.com/astrojuanlu>`,
:literalref:`@bepri<https://github.com/bepri>`,
:literalref:`@cmatsuoka<https://github.com/cmatsuoka>`,
:literalref:`@jahn-junior<https://github.com/jahn-junior>`,
:literalref:`@lengau<https://github.com/lengau>`,
:literalref:`@medubelko<https://github.com/medubelko>`,
:literalref:`@mr-cal<https://github.com/mr-cal>`,
:literalref:`@sergiusens<https://github.com/sergiusens>`,
:literalref:`@soumyaDghosh<https://github.com/soumyaDghosh>`,
:literalref:`@st3v3nmw<https://github.com/st3v3nmw>`,
and :literalref:`@tigarmo<https://github.com/tigarmo>`

.. _Gradle: https://gradle.org/
.. _Rust crates: https://doc.rust-lang.org/book/ch07-01-packages-and-crates.html
.. _Spread: https://github.com/snapcore/spread
.. _cargo registry: https://doc.rust-lang.org/cargo/reference/registries.html
.. _#5107: https://github.com/canonical/snapcraft/issues/5107
.. _#5272: https://github.com/canonical/snapcraft/issues/5272
.. _#5491: https://github.com/canonical/snapcraft/issues/5491
.. _#5522: https://github.com/canonical/snapcraft/issues/5522
