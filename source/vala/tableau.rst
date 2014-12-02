************
Les tableaux
************

Qu'est-ce qu'un tableau en programmation ?
==========================================

Pour faire simple un tableau est une variable
un peu spéciale qui permet de stocker plusieurs valeurs
du même type dans ce dernier.

Une chose primordiale à retenir, la première valeur d'un tableau
est à la potition zéro:

======== === === === === === === ===
Valeur    a   b   c   d   e   f   i

Position  0   1   2   3   4   5   6
======== === === === === === === ===

Comment crée un tableau ?
=========================

Pour faire ce tableau en vala, voici comment faire:

.. code-block:: vala

   string[] tab;

   tab = {"a", "b", "c", "d", "e", "f", "i"};

**Ce qu'il faut retenir:**

  1. On reconnait un tableau par sont type suivi des crochets.
  2. En vala, le tableau est dynamique, il n'est pas recomandé de definir la taille du tableau a l'avance (string[7] par exemple).
  3. Pour initialiser le tableau, ne jamais oublier les acolades.

.. note::

   le nom de la variable, "tab" est juste un exemple.

Comment lire une information dans un tableau ?
==============================================

Souvenez vous bien du tableau Position/Valeur, un tableau commence toujours
par un 0 et fini toujour par "le nombre d'éléments" - 1.

Pour lire un elements dans le tableau, il suffit de donner la position:

.. code-block:: vala

   void main () {
   string[] tab;

   tab = {"a", "b", "c", "d", "e", "f", "i"};
   print ("%s \n%s \n", tab[0], tab[5]);
   }

Le resultat sera:

.. code-block:: text

   a
   f

Cela ne nous choque pas, mais imaginons si je lui demande une position d'une
valeur non déclaré ?

.. code-block:: vala

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d", "e", "f", "i"};
      print ("%s \n, tab[42]);
   }

Donnera :

.. code-block:: text

   (null)

Il nous donne aucune erreur de compilation, sont resulat est juste nul.

.. important::

   Le vala est vraiment bien, le même exemple en c serais un masacre:
   arret du programme, et un jolie "segfault" (segmentation fault).

.. note::

   Cependant, c'est un peut a double tranchant:
   je vous recommande de faire attention avec les valeurs de tableau et de
   toujours vérifier les valeurs de chaque variable avant de faire la fonction.

Ajouter une valeur dans un tableau déjà crée
--------------------------------------------

voici un exemple en vala pour ajouter des valeurs a la suite d'un tabeau:

.. code-block:: vala

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d"};
      tab += "e";
   }


le foreach
==========

Voici la derniere boucle que je vais vous apprendre, le foreach.
Il est parfait pour parcourir et donner les valeurs existante du tableau.

.. code-block:: vala

   foreach (string key in tab){

   }

Le prototype differt selon le langage, mais voici la version de vala:

  1. creation du variable du même type que le tableau: string key
  2. in" pour preciser la variable du tableau, et "tab" est le nom de notre exemple plus haut.
  3. ce qu'il faut retenir c'est qu'a chaque tour de boucle, le foreach deplace la position vers le prochain element existant et le stock dans la variable
"key".

.. code-block:: vala

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d", "e", "f", "i"};
      foreach (string key in tab) {
         print ("%s \n", key);
      }
   }

Le resultat:

.. code-block:: text

   a
   b
   c
   d
   e
   f
   i

Exercice du chapitre
====================

Un peu plus, je vous ai montré comment faire pour ajouter simplement un élément
dans le tableau, mais je ne vous est pas montré comment faire l'inverse !

C'est un bon entrainement que je vous propose la, vous avez toute les cartes en
main pour:

1. Créer une petite fonction qui prend en parametre un tableau et un string
(vive l'informatique...), cette fonction a pour but de suprimer le mot (dans
le string) et de refaire un nouveau tableau.


Correction de l'entrainement:
=============================

fonction pour retirer une valeur dans un tableau
------------------------------------------------

voici la correction du premier exercice:

.. code-block:: vala

   string[] supMot(string[] tab, string mot) {
      string[] newTab = {};

      foreach (string key in tab)
         if (key !=  mot)
            newTab += key;
   }

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d", "e", "f", "i"};
      tab = supMot(tab, "b");
      foreach (string key in tab)
         print ("%s \n", key);
   }

.. note::

   **A retenir:**

   1. Une fonction est toujours au dessus de la fonction "main".
   2. Je n'utilise pas d'acolade si le contenu tien en une ligne.
   3. je respecte l'ordre du prototype de la fonction.
