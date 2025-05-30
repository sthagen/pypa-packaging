Changelog
---------

*unreleased*
~~~~~~~~~~~~

* Change project license metadata to use an SPDX license expression.


25.0 - 2025-04-19
~~~~~~~~~~~~~~~~~

* PEP 751: Add support for ``extras`` and ``dependency_groups`` markers. (:issue:`885`)
* PEP 738: Add support for Android platform tags. (:issue:`880`)

24.2 - 2024-11-08
~~~~~~~~~~~~~~~~~

* PEP 639: Implement License-Expression and License-File (:issue:`828`)
* Use ``!r`` formatter for error messages with filenames (:issue:`844`)
* Add support for PEP 730 iOS tags (:issue:`832`)
* Fix prerelease detection for ``>`` and ``<`` (:issue:`794`)
* Fix uninformative error message (:issue:`830`)
* Refactor ``canonicalize_version`` (:issue:`793`)
* Patch python_full_version unconditionally (:issue:`825`)
* Fix doc for ``canonicalize_version`` to mention ``strip_trailing_zero`` and a typo in a docstring (:issue:`801`)
* Fix typo in Version ``__str__`` (:issue:`817`)
* Support creating a ``SpecifierSet`` from an iterable of ``Specifier`` objects (:issue:`775`)

24.1 - 2024-06-10
~~~~~~~~~~~~~~~~~

* Document ``markers.default_environment()`` (:issue:`753`).
* Add support for Python 3.13 (:issue:`783`).
* Modernise type annotations (:issue:`785`).
* Work around ``platform.python_version()`` returning non PEP 440 compliant version
  for non-tagged CPython builds (:issue:`802`).

24.0 - 2024-03-10
~~~~~~~~~~~~~~~~~

* Do specifier matching correctly when the specifier contains an epoch number
  and has more components than the version (:issue:`683`)
* Support the experimental ``--disable-gil`` builds in packaging.tags
  (:issue:`727`)
* BREAKING: Make optional ``metadata.Metadata`` attributes default to ``None`` (:issue:`733`)
* Fix errors when trying to access the ``description_content_type``, ``keywords``,
  and ``requires_python`` attributes on ``metadata.Metadata`` when those values
  have not been provided (:issue:`733`)
* Fix a bug preventing the use of the built in ``ExceptionGroup`` on versions of
  Python that support it (:issue:`725`)

23.2 - 2023-10-01
~~~~~~~~~~~~~~~~~

* Document calendar-based versioning scheme (:issue:`716`)
* Enforce that the entire marker string is parsed (:issue:`687`)
* Requirement parsing no longer automatically validates the URL (:issue:`120`)
* Canonicalize names for requirements comparison (:issue:`644`)
* Introduce ``metadata.Metadata`` (along with ``metadata.ExceptionGroup`` and ``metadata.InvalidMetadata``; :issue:`570`)
* Introduce the ``validate`` keyword parameter to ``utils.normalize_name()`` (:issue:`570`)
* Introduce ``utils.is_normalized_name()`` (:issue:`570`)
* Make ``utils.parse_sdist_filename()`` and ``utils.parse_wheel_filename()``
  raise ``InvalidSdistFilename`` and ``InvalidWheelFilename``, respectively,
  when the version component of the name is invalid
* Remove support for Python 3.7 (:issue:`783`)

23.1 - 2023-04-12
~~~~~~~~~~~~~~~~~

* Parse raw metadata (:issue:`671`)
* Import underlying parser functions as an underscored variable (:issue:`663`)
* Improve error for local version label with unsupported operators (:issue:`675`)
* Add dedicated error for specifiers with incorrect ``.*`` suffix
* Replace spaces in platform names with underscores (:issue:`620`)
* Relax typing of ``_key`` on ``_BaseVersion`` (:issue:`669`)
* Handle prefix match with zeros at end of prefix correctly (:issue:`674`)

23.0 - 2023-01-08
~~~~~~~~~~~~~~~~~

* Allow ``"extra"`` to be ``None`` in the marker environment (:issue:`650`)
* Refactor ``tags._generic_api`` to use ``EXT_SUFFIX`` (:issue:`607`)
* Correctly handle trailing whitespace on URL requirements (:issue:`642`)
* Fix typing for ``specifiers.BaseSpecifier.filter()`` (:issue:`643`)
* Use stable Python 3.11 in tests (:issue:`641`)
* Correctly handle non-normalised specifiers in requirements (:issue:`634`)
* Move to ``src/`` layout (:issue:`626`)
* Remove ``__about__`` file, in favour of keeping constants in ``__init__`` (:issue:`626`)

22.0 - 2022-12-07
~~~~~~~~~~~~~~~~~

* Explicitly declare support for Python 3.11 (:issue:`587`)
* Remove support for Python 3.6 (:issue:`500`)
* Remove ``LegacySpecifier`` and ``LegacyVersion`` (:issue:`407`)
* Add ``__hash__`` and ``__eq__`` to ``Requirement`` (:issue:`499`)
* Add a ``cpNNN-none-any`` tag (:issue:`541`)
* Adhere to :pep:`685` when evaluating markers with extras (:issue:`545`)
* Allow accepting locally installed prereleases with ``SpecifierSet``  (:issue:`515`)
* Allow pre-release versions in marker evaluation (:issue:`523`)
* Correctly parse ELF for musllinux on Big Endian (:issue:`538`)
* Document ``packaging.utils.NormalizedName`` (:issue:`565`)
* Document exceptions raised by functions in ``packaging.utils`` (:issue:`544`)
* Fix compatible version specifier incorrectly strip trailing ``0`` (:issue:`493`)
* Fix macOS platform tags with old macOS SDK (:issue:`513`)
* Forbid prefix version matching on pre-release/post-release segments (:issue:`563`)
* Normalize specifier version for prefix matching (:issue:`561`)
* Improve documentation for ``packaging.specifiers`` and ``packaging.version``. (:issue:`572`)
* ``Marker.evaluate`` will now assume evaluation environment with empty ``extra``.
  Evaluating markers like ``"extra == 'xyz'"`` without passing any extra in the
  ``environment`` will no longer raise an exception (:issue:`550`)
* Remove dependency on ``pyparsing``, by replacing it with a hand-written parser.
  This package now has no runtime dependencies (:issue:`468`)
* Update return type hint for ``Specifier.filter`` and ``SpecifierSet.filter``
  to use ``Iterator`` instead of ``Iterable`` (:issue:`584`)

21.3 - 2021-11-17
~~~~~~~~~~~~~~~~~

* Add a ``pp3-none-any`` tag (:issue:`311`)
* Replace the blank pyparsing 3 exclusion with a 3.0.5 exclusion (:issue:`481`, :issue:`486`)
* Fix a spelling mistake (:issue:`479`)

21.2 - 2021-10-29
~~~~~~~~~~~~~~~~~

* Update documentation entry for 21.1.

21.1 - 2021-10-29
~~~~~~~~~~~~~~~~~

* Update pin to pyparsing to exclude 3.0.0.

21.0 - 2021-07-03
~~~~~~~~~~~~~~~~~

* PEP 656: musllinux support (:issue:`411`)
* Drop support for Python 2.7, Python 3.4 and Python 3.5.
* Replace distutils usage with sysconfig (:issue:`396`)
* Add support for zip files in ``parse_sdist_filename`` (:issue:`429`)
* Use cached ``_hash`` attribute to short-circuit tag equality comparisons (:issue:`417`)
* Specify the default value for the ``specifier`` argument to ``SpecifierSet`` (:issue:`437`)
* Proper keyword-only "warn" argument in packaging.tags (:issue:`403`)
* Correctly remove prerelease suffixes from ~= check (:issue:`366`)
* Fix type hints for ``Version.post`` and ``Version.dev`` (:issue:`393`)
* Use typing alias ``UnparsedVersion`` (:issue:`398`)
* Improve type inference for ``packaging.specifiers.filter()`` (:issue:`430`)
* Tighten the return type of ``canonicalize_version()`` (:issue:`402`)

20.9 - 2021-01-29
~~~~~~~~~~~~~~~~~

* Run `isort <https://pypi.org/project/isort/>`_ over the code base (:issue:`377`)
* Add support for the ``macosx_10_*_universal2`` platform tags (:issue:`379`)
* Introduce ``packaging.utils.parse_wheel_filename()`` and ``parse_sdist_filename()``
  (:issue:`387` and :issue:`389`)

20.8 - 2020-12-11
~~~~~~~~~~~~~~~~~

* Revert back to setuptools for compatibility purposes for some Linux distros (:issue:`363`)
* Do not insert an underscore in wheel tags when the interpreter version number
  is more than 2 digits (:issue:`372`)

20.7 - 2020-11-28
~~~~~~~~~~~~~~~~~

No unreleased changes.

20.6 - 2020-11-28
~~~~~~~~~~~~~~~~~

.. note:: This release was subsequently yanked, and these changes were included in 20.7.

* Fix flit configuration, to include LICENSE files (:issue:`357`)
* Make ``intel`` a recognized CPU architecture for the ``universal`` macOS platform tag (:issue:`361`)
* Add some missing type hints to ``packaging.requirements`` (issue:`350`)

20.5 - 2020-11-27
~~~~~~~~~~~~~~~~~

* Officially support Python 3.9 (:issue:`343`)
* Deprecate the ``LegacyVersion`` and ``LegacySpecifier`` classes (:issue:`321`)
* Handle ``OSError`` on non-dynamic executables when attempting to resolve
  the glibc version string.

20.4 - 2020-05-19
~~~~~~~~~~~~~~~~~

* Canonicalize version before comparing specifiers. (:issue:`282`)
* Change type hint for ``canonicalize_name`` to return
  ``packaging.utils.NormalizedName``.
  This enables the use of static typing tools (like mypy) to detect mixing of
  normalized and un-normalized names.

20.3 - 2020-03-05
~~~~~~~~~~~~~~~~~

* Fix changelog for 20.2.

20.2 - 2020-03-05
~~~~~~~~~~~~~~~~~

* Fix a bug that caused a 32-bit OS that runs on a 64-bit ARM CPU (e.g. ARM-v8,
  aarch64), to report the wrong bitness.

20.1 - 2020-01-24
~~~~~~~~~~~~~~~~~~~

* Fix a bug caused by reuse of an exhausted iterator. (:issue:`257`)

20.0 - 2020-01-06
~~~~~~~~~~~~~~~~~

* Add type hints (:issue:`191`)

* Add proper trove classifiers for PyPy support (:issue:`198`)

* Scale back depending on ``ctypes`` for manylinux support detection (:issue:`171`)

* Use ``sys.implementation.name`` where appropriate for ``packaging.tags`` (:issue:`193`)

* Expand upon the API provided by ``packaging.tags``: ``interpreter_name()``, ``mac_platforms()``, ``compatible_tags()``, ``cpython_tags()``, ``generic_tags()`` (:issue:`187`)

* Officially support Python 3.8 (:issue:`232`)

* Add ``major``, ``minor``, and ``micro`` aliases to ``packaging.version.Version`` (:issue:`225`)

* Properly mark ``packaging`` has being fully typed by adding a ``py.typed`` file (:issue:`226`)

19.2 - 2019-09-18
~~~~~~~~~~~~~~~~~

* Remove dependency on ``attrs`` (:issue:`178`, :issue:`179`)

* Use appropriate fallbacks for CPython ABI tag (:issue:`181`, :issue:`185`)

* Add manylinux2014 support (:issue:`186`)

* Improve ABI detection (:issue:`181`)

* Properly handle debug wheels for Python 3.8 (:issue:`172`)

* Improve detection of debug builds on Windows (:issue:`194`)

19.1 - 2019-07-30
~~~~~~~~~~~~~~~~~

* Add the ``packaging.tags`` module. (:issue:`156`)

* Correctly handle two-digit versions in ``python_version`` (:issue:`119`)


19.0 - 2019-01-20
~~~~~~~~~~~~~~~~~

* Fix string representation of PEP 508 direct URL requirements with markers.

* Better handling of file URLs

  This allows for using ``file:///absolute/path``, which was previously
  prevented due to the missing ``netloc``.

  This allows for all file URLs that ``urlunparse`` turns back into the
  original URL to be valid.


18.0 - 2018-09-26
~~~~~~~~~~~~~~~~~

* Improve error messages when invalid requirements are given. (:issue:`129`)


17.1 - 2017-02-28
~~~~~~~~~~~~~~~~~

* Fix ``utils.canonicalize_version`` when supplying non PEP 440 versions.


17.0 - 2017-02-28
~~~~~~~~~~~~~~~~~

* Drop support for python 2.6, 3.2, and 3.3.

* Define minimal pyparsing version to 2.0.2 (:issue:`91`).

* Add ``epoch``, ``release``, ``pre``, ``dev``, and ``post`` attributes to
  ``Version`` and ``LegacyVersion`` (:issue:`34`).

* Add ``Version().is_devrelease`` and ``LegacyVersion().is_devrelease`` to
  make it easy to determine if a release is a development release.

* Add ``utils.canonicalize_version`` to canonicalize version strings or
  ``Version`` instances (:issue:`121`).


16.8 - 2016-10-29
~~~~~~~~~~~~~~~~~

* Fix markers that utilize ``in`` so that they render correctly.

* Fix an erroneous test on Python RC releases.


16.7 - 2016-04-23
~~~~~~~~~~~~~~~~~

* Add support for the deprecated ``python_implementation`` marker which was
  an undocumented setuptools marker in addition to the newer markers.


16.6 - 2016-03-29
~~~~~~~~~~~~~~~~~

* Add support for the deprecated, PEP 345 environment markers in addition to
  the newer markers.


16.5 - 2016-02-26
~~~~~~~~~~~~~~~~~

* Fix a regression in parsing requirements with whitespaces between the comma
  separators.


16.4 - 2016-02-22
~~~~~~~~~~~~~~~~~

* Fix a regression in parsing requirements like ``foo (==4)``.


16.3 - 2016-02-21
~~~~~~~~~~~~~~~~~

* Fix a bug where ``packaging.requirements:Requirement`` was overly strict when
  matching legacy requirements.


16.2 - 2016-02-09
~~~~~~~~~~~~~~~~~

* Add a function that implements the name canonicalization from PEP 503.


16.1 - 2016-02-07
~~~~~~~~~~~~~~~~~

* Implement requirement specifiers from PEP 508.


16.0 - 2016-01-19
~~~~~~~~~~~~~~~~~

* Relicense so that packaging is available under *either* the Apache License,
  Version 2.0 or a 2 Clause BSD license.

* Support installation of packaging when only distutils is available.

* Fix ``==`` comparison when there is a prefix and a local version in play.
  (:issue:`41`).

* Implement environment markers from PEP 508.


15.3 - 2015-08-01
~~~~~~~~~~~~~~~~~

* Normalize post-release spellings for rev/r prefixes. :issue:`35`


15.2 - 2015-05-13
~~~~~~~~~~~~~~~~~

* Fix an error where the arbitrary specifier (``===``) was not correctly
  allowing pre-releases when it was being used.

* Expose the specifier and version parts through properties on the
  ``Specifier`` classes.

* Allow iterating over the ``SpecifierSet`` to get access to all of the
  ``Specifier`` instances.

* Allow testing if a version is contained within a specifier via the ``in``
  operator.


15.1 - 2015-04-13
~~~~~~~~~~~~~~~~~

* Fix a logic error that was causing inconsistent answers about whether or not
  a pre-release was contained within a ``SpecifierSet`` or not.


15.0 - 2015-01-02
~~~~~~~~~~~~~~~~~

* Add ``Version().is_postrelease`` and ``LegacyVersion().is_postrelease`` to
  make it easy to determine if a release is a post release.

* Add ``Version().base_version`` and ``LegacyVersion().base_version`` to make
  it easy to get the public version without any pre or post release markers.

* Support the update to PEP 440 which removed the implied ``!=V.*`` when using
  either ``>V`` or ``<V`` and which instead special cased the handling of
  pre-releases, post-releases, and local versions when using ``>V`` or ``<V``.


14.5 - 2014-12-17
~~~~~~~~~~~~~~~~~

* Normalize release candidates as ``rc`` instead of ``c``.

* Expose the ``VERSION_PATTERN`` constant, a regular expression matching
  a valid version.


14.4 - 2014-12-15
~~~~~~~~~~~~~~~~~

* Ensure that versions are normalized before comparison when used in a
  specifier with a less than (``<``) or greater than (``>``) operator.


14.3 - 2014-11-19
~~~~~~~~~~~~~~~~~

* **BACKWARDS INCOMPATIBLE** Refactor specifier support so that it can sanely
  handle legacy specifiers as well as PEP 440 specifiers.

* **BACKWARDS INCOMPATIBLE** Move the specifier support out of
  ``packaging.version`` into ``packaging.specifiers``.


14.2 - 2014-09-10
~~~~~~~~~~~~~~~~~

* Add prerelease support to ``Specifier``.
* Remove the ability to do ``item in Specifier()`` and replace it with
  ``Specifier().contains(item)`` in order to allow flags that signal if a
  prerelease should be accepted or not.
* Add a method ``Specifier().filter()`` which will take an iterable and returns
  an iterable with items that do not match the specifier filtered out.


14.1 - 2014-09-08
~~~~~~~~~~~~~~~~~

* Allow ``LegacyVersion`` and ``Version`` to be sorted together.
* Add ``packaging.version.parse()`` to enable easily parsing a version string
  as either a ``Version`` or a ``LegacyVersion`` depending on it's PEP 440
  validity.


14.0 - 2014-09-05
~~~~~~~~~~~~~~~~~

* Initial release.


.. _`master`: https://github.com/pypa/packaging/
