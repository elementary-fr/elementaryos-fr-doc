Contractor
==========

Ressource pour l'écriture d'une doc ou d'un tutoriel: 

* Exemple de fichier : https://launchpadlibrarian.net/84018890/compress.contract

* Documentation officielle: http://elementaryos.org/docs/human-interface-guidelines/contractor

Les fichiers sont stockés dans `/usr/share/contractor/`

Format des fichiers .contract
=============================

.. code-block::

  [Contractor Entry]
  Name=Archives
  Icon=file-roller
  Description=Create archive
  MimeType=all
  Exec=file-roller -d %U
