Changelog
=========

.. include:: includes/all.rst

**debops-keyring**

This project adheres to `Semantic Versioning <http://semver.org/spec/v2.0.0.html>`__
and `human-readable changelog <http://keepachangelog.com/en/0.3.0/>`__.

The current repository maintainer is drybjed_.


`debops-keyring master`_ - unreleased
-------------------------------------

.. _debops-keyring master: https://github.com/debops/debops-keyring/compare/v0.2.1...master

Added
~~~~~

- Add Tobias Mueller's OpenPGP key as DebOps Contributor. [muelli_]

Fixed
~~~~~

- :command:`git log '--format=%H %G?'` handles signatures made by an expired
  OpenPGP subkey improperly by marking the commit as "N" (no signature).
  This breaks the history checking and the enforcement that all commits MUST be
  signed. The workaround is to only check the HEAD commit in the assumption
  that the subkey used to sign it is not expired. [ypid_]

- OpenPGP keys can have multiple subkeys. This is not interpreted as an error
  anymore as long as one of the keys is the public key with the matching key
  fingerprint. [ypid_]


`debops-keyring v0.2.1`_ - 2016-09-15
-------------------------------------

.. _debops-keyring v0.2.1: https://github.com/debops/debops-keyring/compare/v0.2.0...v0.2.1

Added
~~~~~

- Add OpenPGP key ``0xDAA9DC5E750C1E85`` (Aleksey Gavrilov) as DebOps
  Contributor. [drybjed_]

- Add REQUIREMENTS which are enforced by CI tests also to the README. [ypid_]

- Add RECOMMENDATION for an asymmetric public-key size of at least 3248 bits
  (for RSA). [ypid_]

Changed
~~~~~~~

- Moved role files to :file:`roles/` directory to keep the root of the
  repository clean. [ypid_]

- Clarify the requirements for additional OpenPGP key proofs for DebOps
  Contributors and DebOps Developers. [drybjed_]

- Key uploading and updating to `sks-keyservers.net`_ (or another OpenPGP
  keyserver pools which sync with `sks-keyservers.net`_) is now
  REQUIRED. [ypid_]


`debops-keyring v0.2.0`_ - 2016-08-07
-------------------------------------

.. _debops-keyring v0.2.0: https://github.com/debops/debops-keyring/compare/v0.1.1...v0.2.0

Added
~~~~~

- Added note intended to get DebOps Developers and DebOps Contributors to think
  about OpSec related to their OpenPGP setup. [ypid_]

- Created the :file:`contributors` file to list the DebOps Contributors. [ypid_]

- Created the :file:`bots` file to list the DebOps Bots. [ypid_]

- Generate documentation from the machine readable debops-keyring files using a
  Python 3 script/module. [ypid_]

- Use the Python 3 script/module for consistency checking of the
  debops-keyring. [ypid_]

- Enforce minimum key size (>=2048) of all keys in the debops-keyring. [ypid_]

- Enforce that all commits in the debops-keyring are signed by a public
  key present in the keyring (as of :command:`git` HEAD). [ypid_]

- Require a signed :command:`git` commit with the most trusted OpenPGP subkey to add
  or change the corresponding public keys. [ypid_]

- Note that public keys should be uploaded and kept up-to-date on
  sks-keyservers.net_.

Changed
~~~~~~~

- Renamed :file:`admin` file to :file:`admins`. There might be multiple admins. [ypid_]

- Use the term "OpenPGP" when not specifically referring to the GnuPG
  implementation. [ypid_]


`debops-keyring v0.1.1`_ - 2016-07-10
-------------------------------------

.. _debops-keyring v0.1.1: https://github.com/debops/debops-keyring/compare/v0.1.0...v0.1.1

Added
~~~~~

- Add OpenPGP keys ``0x86FD980BBF1A40F8``, ``0x5FE92C12EE88E1F0``,
  ``0x489A4D5EC353C98A`` (Robin Schneider). Refer to `this comment
  <https://github.com/debops/ansible-ifupdown/pull/48#issuecomment-212146099>`_
  for details how I am using the three OpenPGP keys. [ypid_]

- Wrote initial "Adding your OpenPGP public key" and "Becoming a DebOps Developer"
  sections. [ypid_]

- Created the :file:`leader` files which defines the DebOps Project Leader. [ypid_]

- Created the :file:`admin` file which defines the DebOps Project Admin. [ypid_]

- Created the :file:`developers` files which lists the DebOps Developers. [ypid_]


debops-keyring v0.1.0 - 2016-07-10
----------------------------------

Added
~~~~~

- Initial release. [drybjed_]

- Add OpenPGP key ``0x2DCCF53E9BC74BEC`` (Maciej Delmanowski). [drybjed_]
