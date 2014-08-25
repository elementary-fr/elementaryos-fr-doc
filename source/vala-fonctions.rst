
**************************
Les bases du langage Vala
**************************

Dans cette partie, nous allons apprendre les toutes permières bases du Vala.

Les Fontions
=========================

Dans la partie précédente, nous avons créer un premier programme dont le code
était le suivant:

.. code-block
   :linenos:

   void main (){
       print("Hello Wolrd\n");
   }

Dans ce fichier, on trouve une fonction, appelée main ("principale"), et une
instruction *print("Hello Wolrd!\n");* .

Nous allons approfondire le concept de fonction plus tard. Pour l'instant,
il suffit de savoir qu'une fonction, c'est un repère pour le compilateur.

Le compilateur sais que le programme commence à la fonction main. Ainsi,
la première ligne exécutée sera la première ligne (et unique) ligne située
entre les accolades.

Cette ligne, c'est l'instruction *print("Hello Wolrd\n");* . Cette instruction
appèle en réalité la fonction print, qui est fournie par Vala. Toutes les 
instructions se termine par un point virgule.

.. note
   Vous remarquerez la présence d'un *\n* dans *Hello World\n"*, la fonction
   print, c'est un symbole spéciale qui est compris par le compilateur comme
   étant le caractère *retour ligne*. Essayé de l'enlevé, de recompiler et
   de réexécuter le programme, pour voir à quoi il sert exactement


Lorsqu'un programme arrive à l'accolade fermante d'une fonction *main*,
celui ci se termine.

Création d'une fonction
=======================

Si nous devons écrire plusieurs fois le message *Hello World* , on pourrait
le faire de la manière suivante:

.. code-block
   :linenos:

   void main (){
       print("Hello Wolrd\n");
       print("Hello Wolrd\n");
       print("Hello Wolrd\n");
       print("Hello Wolrd\n");
   }

Mais, nous pouvons aussi le faire d'une manière différent, par exemple en créant
une fonction *dit_bonjour*. Le code est le suivant:

.. code-block
   :linenos:

   void main (){
       dit_bonjour();
       dit_bonjour();
       dit_bonjour();
       dit_bonjour();
   }

   void dit_bonjour () {
       print("Hello Wolrd\n");
   }

Ce code fait exactement la même chose que le code précédant.

Essayer à présent de rajouter une fonction *dit_aurevoire* , qui affiche
le texte *Goodbye World* .

Les variables
=============

Une variable est une référence vers un emplacement mémoire.

Par exemple, le code suivant:

.. code-block
   :linenos:

   void main (){
       print("Bonjour");

       var texte = "Au revoir";
       print(texte);


   }

Dans la première instruction, le programme va écrire "Bonjour" dans la 
mémoire vive de l'ordinateur et va l'envoyé à la
fonction print. Ensuite, comme il n'en a plus besoin, il la supprime de la 
mémoire;


