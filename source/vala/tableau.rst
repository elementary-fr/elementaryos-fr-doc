************
Les tableaux
************

Qu'est-ce qu'un tableau en programmation ?
==========================================

Pour faire simple un tableau est une variable
un peu spéciale qui permet de stocker plusieurs valeurs
du même type dans ce dernier.

Une chose primordiale à retenir, la première valeur d'un tableau
est à la position zéro:

======== === === === === === === ===
Valeur    a   b   c   d   e   f   i

Position  0   1   2   3   4   5   6
======== === === === === === === ===

Comment créer un tableau ?
==========================

Pour faire ce tableau en Vala, voici comment faire:

.. code-block:: vala

   string[] tab;

   tab = {"a", "b", "c", "d", "e", "f", "i"};

**Ce qu'il faut retenir:**

  1. On reconnait un tableau par son type suivi des crochets.
  2. En Vala, le tableau est dynamique, il n'est pas recommandé de définir la 
     taille du tableau a l'avance (string[7] par exemple).
  3. Pour initialiser le tableau, ne jamais oublier les accolades.

.. note::

   Le nom de la variable utilisée ci-dessus, "tab" est juste un exemple.

Comment lire une information dans un tableau ?
==============================================

Souvenez vous bien du tableau Position/Valeur, un tableau commence toujours
par un 0 et fini toujours par "le nombre d'éléments" - 1.

Lire une valeur
---------------

Pour lire un élément dans le tableau, il suffit de donner sa position:

.. code-block:: vala

   void main () {
   string[] tab;

   tab = {"a", "b", "c", "d", "e", "f", "i"};
   print ("%s \n%s \n", tab[0], tab[5]);
   }

Le résultat sera:

.. code-block:: text

   a
   f

Cela ne nous choque pas, mais imaginons si je lui demande une position d'une
valeur non déclarée ?

.. code-block:: vala

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d", "e", "f", "i"};
      print ("%s \n, tab[42]);
   }

Donnera :

.. code-block:: text

   (null)

Il ne nous donne aucune erreur de compilation, son résultat est juste nul.

.. important::

   Le vala est vraiment bien, le même exemple en c serait un massacre:
   arrêt du programme, et un joli "segfault" (segmentation fault).

.. note::

   Cependant, c'est un peu à double tranchant:
   je vous recommande de faire attention avec les valeurs de tableau et de
   toujours vérifier les valeurs de chaque variable avant de faire la fonction.

Lire plusieurs valeurs
-----------------------

Cela n'est pas plus dur que pour une seule valeur, admettons que je souhaite prendre
plusieurs valeurs dans un tableau pour les copier vers un autre tableau:

.. code-block:: vala

   void main () {
      string[] tab;
      string[] exp;

      tab = {"a", "b", "c", "d", "e", "f", "i"};
      exp = tab[1:3];
   }

Quel sera le résultat ? Et bien, **exp** a maintenant **"b"** et **"c"**.
Pourquoi pas le **"d"** ? On peut dire qu'il fait quelque chose comme:
"on démarre à l'index 1, et on prend juste avant l'index 3".


.. note::

   Les tableaux sont un élément important, je vous invite à faire des tests
   pour mieux comprendre leurs comportements.

Ajouter une valeur dans un tableau déjà créé
---------------------------------------------

Voici un exemple en Vala pour ajouter des valeurs à la suite d'un tableau:

.. code-block:: vala

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d"};
      tab += "e";
   }


Le foreach
==========

Voici la dernière boucle que je vais vous apprendre, le foreach.
Elle est parfaite pour parcourir et retourner les valeurs existantes du tableau.

.. code-block:: vala

   foreach (string key in tab){

   }

**Le prototype differt selon le langage, mais voici la version de Vala:**

  1. Création d'une variable du même type que le tableau: **string key**.
  2. **"in"** pour préciser la variable du tableau, et **"tab"** est le nom de
     notre exemple plus haut.
  3. Ce qu'il faut retenir c'est qu'à chaque tour de boucle, le foreach déplace
     la position vers le prochain élément existant et le stocke dans la variable
     "key".

.. code-block:: vala

   void main () {
      string[] tab;

      tab = {"a", "b", "c", "d", "e", "f", "i"};
      foreach (string key in tab) {
         print ("%s \n", key);
      }
   }

Le résultat:

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
dans le tableau, mais je ne vous ai pas montré comment faire l'inverse !

C'est un bon entrainement que je vous propose la, vous avez toute les cartes en
main pour:

1. Créer une petite fonction qui prend en paramètre un tableau et un string
(vive l'informatique...), cette fonction a pour but de supprimer le mot (dans
le string) et de refaire un nouveau tableau.


Correction de l'entrainement:
=============================

Fonction pour retirer une valeur dans un tableau
------------------------------------------------

Voici la correction du premier exercice:

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

   **À retenir:**

   1. Une fonction est toujours au dessus de la fonction "main".
   2. Je n'utilise pas d'accolade si le contenu tiens en une ligne.
   3. Je respecte l'ordre du prototype de la fonction.
