
**************************
Les bases du langage Vala
**************************

Dans cette partie, nous allons apprendre les toutes permières bases du Vala.

Les Fontions
=========================

Dans la partie précédente, nous avons créé un premier programme dont le code 
était le suivant:

.. code-block:: vala
   :linenos:

   void main (){
       print("Hello World\n");
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

.. note::
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

.. code-block:: vala
   :linenos:

   void main (){
       print("Hello Wolrd\n");
       print("Hello Wolrd\n");
       print("Hello Wolrd\n");
       print("Hello Wolrd\n");
   }

Mais, nous pouvons aussi le faire d'une manière différent, par exemple en créant
une fonction *dit_bonjour*. Le code est le suivant:

.. code-block:: vala
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

.. code-block:: vala
   :linenos:

   void main (){
       print("Bonjour");

       var texte = "Au revoir";
       print(texte);


   }

Dans la première instruction, le programme va écrire *Bonjour* dans la 
mémoire vive de l'ordinateur et va l'envoyé à la fonction print. Ensuite, comme 
il n'en a plus besoin, il la supprime de la mémoire.

La ligne var *texte = "Au revoir"* va elle écrire dans la mémoire aurevoire,
le compilateur va retenir son adresse et l'associé à l'utilisation de *texte*.

Cette association marche uniquement à l'intérieur de la fonction dans laquelle
la variable a été déclarée.

Le mot clef *var* est passe partout, il laisse le champ libre au compilateur
sur la manière dans *"Au revoir"* est interprété.

Ainsi, le format de stockage sera différent entre:

.. code-block:: vala
   :linenos:

   var text = "bonjour";
   var nombre = 2;
   var nombre_second = 2.2;

Le premier est stocké en tant que chaine de caractère, le deuxième en tant que
nombre décimal signé.

.. note::
   Signé signifie que le nombre peut être négatif

Le troisième est lui stocké comme nombre à virgule flottante.

Il y a un autre mode de déclaration des variables. Dans ce mode, c'est nous qui
choissons le format de stockage final.

Reprenant l'exemple précédent avec ce nouveau mode:

.. code-block:: vala
   :linenos:

   string text = "bonjour";
   int nombre = 2;
   float nombre_second = 2.2;

.. note::
   Les mots string, int et float sont appelés des *types*


