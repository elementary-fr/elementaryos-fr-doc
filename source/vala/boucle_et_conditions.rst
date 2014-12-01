*********************************
Les instructions conditionnelles
*********************************

Dans nos programmes Vala, nous allons régulièrement avoir besoin de faire des
opérations en fonction d'un résultat précédent. Par exemple, lors d'un processus
de connexion à une application, si le login et le mot de passe sont bons,
alors nous pouvons nous connecter, sinon nous afficherons une erreur.

Il s'agit de ce que l'on appelle une condition. Elle est évaluée lors de
l'exécution et en fonction de son résultat (vrai ou faux) nous ferons telle ou
telle chose.

Bien que relativement court, ce chapitre est très important. N'hésitez pas à le
relire et à vous entraîner.

Les opérateurs de comparaison
=============================

Une condition se construit grâce à des opérateurs de comparaison. On dénombre
plusieurs opérateurs de comparaisons, les plus courants sont :

=========  ========================
Opérateur  Description
=========  ========================
==         Egalité

!=         Différence

>          Supérieur à

<          Inférieur à

>=         Supérieur ou égal

<=         Inférieur ou égal

&&         ET logique

||         OU logique

!          Négation
=========  ========================

Nous allons voir comment les utiliser en combinaison avec les instructions
conditionnelles.

L'instruction *if*
=====================

L'instruction **if** permet d'exécuter du code si une condition est vraie
(if = si en anglais).

Par exemple :

.. code-block:: vala

   int compte_en_banque = 300;
   if (compte_en_banque >= 0)
       print("Votre compte est créditeur\n");

Ici, nous avons une variable contenant le solde de notre compte en banque. Si
notre solde est supérieur ou égal à 0 alors nous affichons que le compte est
créditeur.

Pour afficher que le compte est débiteur, on pourrait tester si la valeur de la
variable est inférieure à 0 et afficher que le compte est débiteur :

.. code-block:: vala
   :linenos:

   int compte_en_banque = 300;
   if (compte_en_banque >= 0)
       print("Votre compte est créditeur\n");
   if (compte_en_banque < 0)
       print("Votre compte est débiteur\n");

Une autre solution est d’utiliser le mot clé **else**, qui veut dire « sinon »
en anglais.

« Si la valeur est vraie, alors on fait quelque chose, sinon, on fait autre
chose », ce qui se traduit en Vala par :

.. code-block:: vala
   :linenos:

   int compte_en_banque = 300;
   if (compte_en_banque >= 0)
       print("Votre compte est créditeur\n");
   else
       print("Votre compte est débiteur\n");

Il faut bien se rendre compte que l’instruction if teste si une valeur est vraie
(dans l’exemple précédent la comparaison compte_en_banque >= 0).

On a vu rapidement dans les chapitres précédents qu’il existait un type de
variable qui permettait de stocker une valeur vraie ou fausse : le type bool,
autrement appelé booléen (boolean en anglais).

Ainsi, il sera également possible de tester la valeur d’un booléen. L’exemple
précédent peut aussi s’écrire :

.. code-block:: vala
   :linenos:

   int compte_en_banque = 300;
   int est_crediteur = (compte_en_banque >= 0);
   if (est_crediteur)
       print("Votre compte est créditeur\n");
   else
       print("Votre compte est débiteur\n");

À noter que les parenthèses autour de l’instruction de comparaison sont
facultatives, je les ai écrites ici pour clairement identifier que la variable
*est_crediteur* va contenir une valeur qui est le résultat de l’opération de
comparaison « compte en banque est supérieur ou égal à 0 », en l’occurrence
vrai.

Voici d’autres exemples pour vous permettre d’appréhender plus précisément le
fonctionnement du type bool :

.. code-block:: vala
   :linenos:

   int age = 30;
   bool est_age_de_30_ans = (age == 30); // Valeur vrai (true)
   bool est_superieur_a_10 = age > 10; // Valeur vrai (true)
   bool est_different_de_30 = age != 30; // Valeur fausse (false)

Combinaison
-----------

Il est également possible de combiner les tests grâce aux opérateurs de logique
conditionnelle, par exemple && qui correspond à l’opérateur *ET*.

Dans l’exemple qui suit, nous affichons le message de bienvenue uniquement si le
login est « Nicolas » ET que le mot de passe est « test ». Si l’un des deux ne
correspond pas, nous irons dans l’instruction **else**.

.. code-block:: vala
   :linenos:

   string login = "Nicolas";
   string mot_de_passe = "test";
   if (login == "Nicolas" && mot_de_passe == "test")
       print("Bienvenue Nicolas\n");
   else
       print("Login incorrect\n");

.. note::
   Remarquons ici que nous avons utilisé le test d’égalité **==**, à ne pas
   confondre avec l’opérateur d’affection **=**. C’est une erreur classique de
   débutant.

D’autres opérateurs de logiques existent, nous avons notamment l’opérateur
**||** qui correspond au *OU* logique :

.. code-block:: vala
   :linenos:

   if (civilite == "Mme" || civilite == "Mlle")
       print("Vous êtes une femme\n");
   else
       print("Vous êtes un homme\n");

L’exemple parle de lui-même, si la civilité de la personne est *Mme* ou *Mlle*,
alors nous avons à faire à une femme.

A noter ici que si la première condition du **if** est vraie alors la deuxième
ne sera pas évaluée. C’est un détail ici, mais cela peut s’avérer important dans
certaines situations dont une que nous verrons un peu plus loin.

Un autre opérateur très courant est la négation que l’on utilise avec
l’opérateur **!**. Par exemple :

.. code-block:: vala
   :linenos:

   bool est_vrai = true;
   if (!est_vrai)
       print("C'est faux !\n");
   else
       print("C'est vrai !\n");

Ce test pourrait se lire ainsi : « Si la négation de la variable *est_vrai* est
vraie, alors on écrira c’est faux ».

La variable « est_vrai » étant égale à *true*, sa négation vaut *false*.

Dans cet exemple, le programme nous affichera donc l’instruction correspondant
au **else**, à savoir « C’est vrai ! ».

Rappelez-vous, nous avons dit qu’une instruction se finissait en général par un
point-virgule. Comment cela se fait-il alors qu’il n’y ait pas de point-virgule
à la fin du if ou du else ?

Et si nous écrivions l’exemple précédent de cette façon ?

.. code-block:: vala
   :linenos:

   bool est_vrai = true;
   if (!est_vrai) print("C'est faux !\n");
   else print("C'est vrai !\n");

Ceci est tout à fait valable et permet de voir où s’arrête vraiment
l’instruction grâce au point-virgule. Cependant, nous écrivons en général ces
instructions de la première façon afin que celles-ci soient plus lisibles.

Vous aurez l’occasion de rencontrer dans les chapitres suivants d’autres
instructions qui ne se terminent pas obligatoirement par un point-virgule.

.. note:
   Nous verrons dans le chapitre suivant comment exécuter plusieurs instructions
   après une instruction conditionnelle en les groupant dans des blocs de code.

Remarquons enfin qu'il est possible d’enchaîner les tests de manière à traiter
plusieurs conditions en utilisant la combinaison **else if**. Cela donne :

.. code-block:: vala
   :linenos:

   if (civilite == "Mme")
       print("Vous êtes une femme\n");
   else if (civilite == "Mlle")
       print("Vous êtes une femme non mariée\n");
   else if (civilite == "M.")
       print("Vous êtes un homme\n");
   else
       print("Je n'ai pas pu déterminer votre civilité\n");


Notion très avancer: Les ternaires
==================================

Les ternaires sont ni plus ni moins qu'un if/else qui a la particulariter de
tenir sur une ligne. on les utilses pour envoyer une information dans une
variable voir un return.

.. note::

  Si vous venez tous juste d'apprendre la programmation, vous pouvez passer cette
  partie, cepandant il est important de savoir utiliser a la fin de ce cours.

.. code-block:: vala

   void main () {
      string nom = "Nolan";
      print ((nom == "Nolan")? "oui \n" : "non \n");
   }

Le resultat est:

.. code-block::

   oui

Explication
-----------

Pour mon exemple, je retourne une condition a un print, la lecture en pseudo code serait:

.. code-block::
   affiche ((condition)si "alors" sinon "ca");

La conditions est avant le **si (?)**, et pour le **sinon (:)**  ne se ferme
que avec la premier paranthese.

.. important::

   Contrirement au **if**, il est obligatoire d'avoir un **else** dans une ternaire.

   dans le cas que vous utilisez une ternaire sur une variable, je vous conseil de retourner la même variable

Voici un exemple un peu plus concret:

.. code-block:: vala

   void main () {
      int nb = -5;

      nb = ((nb < 0)? nb * -1 : nb);
      print ("%d \n", nb);
   }

Admeton que pour une raison x ou y je cherche a convertir un nombre negatif
en nombre positif, la solution la plus ergonomique serait de faire une ternaire.
Dans le cas contraire, si nb est superieur a 0, nb serais devenu nb.

une, deux ou trois ternaire dans une ternaire
---------------------------------------------

le prototype d'une ternaire imbriqué est la suivante:

.. code-block::
   affiche ((condition)si "alors" sinon ((condition2)si "alors" sinon "ca"));

Pour rendre plus lisible la deuxieme ternaire, je vous conseil de le placer
dans une paranthese.

L'instruction **switch**
=========================

L’instruction **switch** peut être utilisée lorsqu’une variable peut prendre
beaucoup de valeurs. Elle permet de simplifier l’écriture.

Ainsi, le code précédant peut aussi s'écrire de la manière suivante :

.. code-block:: vala
   :linenos:

   switch(civilite) {
       case "Mme":
           print("Vous êtes une femme\n");
           break;
       case "Mlle":
           print("Vous êtes une femme non mariée\n");
           break;
       case "m.":
           print("Vous êtes un homme\n");
           break;
       default:
            print("Je n'ai pas pu déterminer votre civilité\n");
            break;
   }

**switch** commence par évaluer la variable qui lui est passée entre
parenthèses. Avec le mot clé **case** on énumère les différents cas possible
pour la variable et on exécute les instructions correspondante jusqu’au mot clé
**break** qui signifie que l’on sort du **switch**.

Nous pouvons également enchaîner plusieurs cas pour qu’ils fassent la même
chose, ce qui reproduit le fonctionnement de l’opérateur logique **||** (OU).

Par exemple :

.. code-block:: vala
   :linenos:

   switch (mois) {
       case "Mars":
       case "Avril":
       case "Mai":
           print("C'est le printemps\n");
           break;
       case "Juin":
       case "Juillet":
       case "Aout":
           print("C'est l'été\n");
           break;
       case "Septembre":
       case "Octobre":
       case "Novembre":
           print("C'est l'automne\n");
           break;
       case "Décembre":
       case "Janvier":
       case "Février":
           print("C'est l'hiver\n");
           break;
   }

.. note::

   Il n'est pas obligatoir de retenir le switch, il reste très pratique pour
   faire les menus, mais facilement remplacable par une boucle avec des if.

les boucles
===========

Cette instruction permet de repeter une action tant que la condition est valide,
il en existe trois, le troisieme etant quelque peut special, nous le vérons dans
le chapitre des tableaux.

l'instruction while
-------------------

**while (condition)** sigifie **tant que condition est vrais, on revient à la
même ligne**.

.. code-block:: vala
   :linenos:

   void main () {
      int entier = 0;
      while (entier <= 5) {
        print ("%d \n", entier);
        entier++;
      }
   }

Le resultat attendu:

.. code-block::

   0
   1
   2
   3
   4
   5


.. note::

   c'est clairement la plus importante instruction de boucle, avec un peu de
   reflexion, il est possible de ce passer des deux prochaines instruction.

l'instruction do ... while
--------------------------

le **do ... while** est la même chose que notre while plus haut. Cependant ,
il ne réagit pas au même regle: la particulariter de cette derniere est de
faire un tour dans la boucle avant tous de chose, puis, si la condition est
correcte de continuer tant qu'elle est vrai.

.. code-block:: vala

   void main  () {
      int entier = 0;
      do {
         print ("%d \n", entier);
         entier++;
      } while (entier <= 10);
   }

Avec cette condition, le resulta sera :

.. code-block::

   0
   1
   2
   3
   4
   5
   6
   7
   8
   9
   10

Maintenant, si je change la condition:

.. code-block:: vala

   void main  () {
      int entier = 0;
      do {
         print ("%d \n", entier);
         entier++;
      } while (entier >= 10);
}

Le resultat sera:

.. code-block::

  0


l'instruction for
-----------------

Le **for** est un peu paticulier, il permet de créer une variable et de
l'initialiser, très utiles pour faire un compteur. L'avatage de cette methode
est de ne pas perdre une ligne avec la creation de la variable.

.. code-block:: vala
   void main () {
      int entier = 10;
      for (int i = 0; entier >= i ; i++ ) {
         print ("%d \n", i);
      }
   }

le resultat de ce code sera:

.. code-block::

   0
   1
   2
   3
   4
   5
   6
   7
   8
   9
   10

En résumé

- Les instructions conditionnelles permettent d'exécuter des instructions
  seulement si une condition est vérifiée.
- On utilise en général le résultat d'une comparaison dans une instruction
  conditionnelle.
- Le Vala possède beaucoup d'opérateurs de comparaison, comme l'opérateur
  d'égalité **==**, l'opérateur de supériorité **>**, d'infériorité **<**, etc.
