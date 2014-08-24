*************
Style de code
*************

.. important::
   Cette section est une traduction non-officiel de la page "code style"
   du site d'elementary OS, disponible à l'adresse suivante:
   http://elementaryos.org/docs/code/code-style

   Tous comme le texte original, et le reste de ce site, ce contenu est publié
   sous license Creative Commons CC BY-SA 3.0


Le but de ce guide est de fournir des intructions claires et précises
sur la manière d'écrire du bon code dans tous les projets elementary.
C'est ligne directrice doit être suivie sur tous les fichiers, de manière
à garder notre code cohérent et lisible.
Nous héritons aussi de certaine des lignes directrices de Gnome pour Vala,
de manière à garder notre code cohérent avec les autres programmes Vala.

Si les lignes directrices proposée ici sont suivie, les nouveaux
arrivant pourront plus facilement se joindre au développement d'elementary et
comprendre le code.
En plus, celà rendra plus facile pour tous les développeurs de travailler sur
des applications dont ils n'ont pas l'habitude, parceque le code sera conforme
à leur habitude. Finallement, comme le dit Guido Van Rossum [#1]_ *Le code est
plus souvent lu qu'écrit* .
Ainsi, en avoir un bien écrit est crucial.



Information
============

Ce guide n'est pas encores, bien qu'il a été discuté et partiellement approuvé
par les contributeurs d'elementary. [#2]_ Il est sujet au changement dans un
futur proche.

Espace blanc
============

Il n'y a pas d'espace blanc traînant à la fin d'une line, qu'elle soit
vide ou non. Il n'y a pas de ligne vide après la déclaration de la
fonction

.. code-block:: vala
   :linenos:

   public string get_text () {
       string text = search_entry.get_text ();
       return text;
   }

Un espace est mis avant l'ouverture de parentaise:

.. code-block:: vala
   :linenos:

   public string get_text () {}
   if (a == 5) return 4;
   for (i = 0; i < maximum; i++) {}
   my_function_name ();
   Object my_instance = new Object ();

Un espace est mis dans tous les endrois ou des opérations mathématique sont
utilisée, entre les nombres et les opérateurs.

.. code-block:: vala
   :linenos:

   c = n * 2 + 4;

Indentation
===========

Le code en Vala est indenté en utilisant 4 espaces pour la cohérence et la
lisibilité.

Dans les classes, les fonctions, les boucles et le contrôle du flux, la première
accolade se met à la fin de la première ligne [#3]_ , suivie par le code indenté
et une ligne de fermeture de la fonction avec une accolade fermante.

.. code-block:: vala
   :linenos:

   public int my_function (int a, string b, long c, int d, int e) {
       if (a == 5) {
           b = 3;
           c += 2;
           return d;
       }

       return e;
   }

Dans les conditions et les boucles, si il n'y a qu'une seule ligne de code, les accolades
ne sont pas utilisées:

.. code-block:: vala
   :linenos:

   if (my_var > 2)
       print ("hello\n");

Pour les instructions else et else if, on utilise le style emboités.

.. code-block:: vala
   :linenos:

   if (a == 4) {
       b = 1;
       print ("Yay");
   } else if (a == 3) {
       b = 3;
       print ("Not so good...");
   } else {
       b = 5;
       print ("Terrible!");
   }

Classes et fichiers
===================

Il est recommandé de n'avoir qu'un classe par fichier.

Tous les fichiers ont le nom de la classe qu'il contiennent.

Le code doit être séparer en classes pour permettre une évolution
plus facile.


Commentaires
============

Les commentaires sont soit sur la même ligne que le code, soit
sur une ligne à part.

Les commentaires sont indentés sur le coté du code, et les commentaires
Comments are either on the same line as the code or in a special line.

Comments are indented alongside the code. Les commentaires évident doivent
être éviter. Il font plus de mal que de bien.

.. code-block:: vala
   :linenos:

   /* User chose number five */
   if (a == 5) {
       B = 4;           // Update value of b
       c = 0;           // No need for c to be positive
       l = n * 2 + 4;   // Clear l variable
   }

Nom de variables, de classes et de fonctions
============================================

.. code-block:: vala
   :linenos:

   my_variable = 5;      // Variable names
   MyClass               // Class names
   my_function_name ();  // Type/Function/Method names
   MY_C       // Constants are all caps with underscores

   /* For enum members, all uppercase and underscores */
   enum OperatingSystem { // An enum name is the same as ClassesNames
       UBUNTU,
       ELEMENTARY_OS,
       VERY_LONG_OS_NAME
   }

Il faut également convenir, qu'il n'y as pas d'utilisation de la notation Hongroise [#4]_ , ni de mélange
entre plusieurs sorte de notation.

Espace de noms de Vala
======================

Se référer à la GLib n'est pas nécessaire. Si vous voulez afficher quelque chose:

.. code-block:: vala
   :linenos:

    GLib.print ("Hello World");
    print ("Hello World");

Choisissez la deuxième méthode, elle est plus propre.

Nombre de colonne par ligne
===========================

Idéalement, il ne devrait pas y avoir plus de 80 caractères par lignes, car c'est la taille
par défaut du terminal. Cependant, exceptionnellement, plus de caractère peuvent être ajouter,
parce que les gens ont aujourd'hui des écrans suffisament large.

La limite maximale est de 120 caractère.

Entête de la license GPL
========================

.. code-block:: vala
   :linenos:

   /***
     Copyright (C) 2011-2012 Application Name Developers
     This program is free software: you can redistribute it and/or modify it
     under the terms of the GNU Lesser General Public License version 3, as published
     by the Free Software Foundation.
     This program is distributed in the hope that it will be useful, but
     WITHOUT ANY WARRANTY; without even the implied warranties of
     MERCHANTABILITY, SATISFACTORY QUALITY, or FITNESS FOR A PARTICULAR
     PURPOSE. See the GNU General Public License for more details.
     You should have received a copy of the GNU General Public License along
     with this program. If not, see
   ***/

.. [#1] Créateur du language python
.. [#2] Dans sa version anglaise
.. [#3] One True Brace Style
.. [#4] Voire http://fr.wikipedia.org/wiki/Notation_hongroise