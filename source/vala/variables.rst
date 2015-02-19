**************
Les variables
**************

Qu’est-ce qu’une variable ?
===========================

Comme tous les langages de programmation, le Vala va pouvoir conserver des
données grâce à des variables. Ce sont en fait des blocs de mémoire qui vont
contenir des nombres, des chaînes de caractères, des dates ou plein d’autres
choses.

Les variables vont nous permettre d’effectuer des calculs mathématiques,
d’enregistrer l’âge du visiteur, de comparer des valeurs, ...etc.

Une variable est représentée par son nom, caractérisée par son type et contient
une valeur.

.. note::

    Le type correspond à ce que la variable représente : un entier, une chaîne
    de caractères, une date, ...etc.

Déclaration/initialisation de variable
======================================

Déclaration
-----------

Voici un exemple de **déclaration** pour chaque type de variable :

.. code-block:: vala

  int nombre;

.. note::
   On appelle ceci la déclaration de la variable.

.. important::
   *int* correspond au début de "integer" qui veut dire "entier" en anglais.

Initialisation
--------------

Dans cette exemple plus haut, la variable n'a pas été initialisé. Elle ne
pourra pas être utilisée car le compilateur ne sait pas quelle valeur il y a dans la variable.

Pour l’initialiser (on parle également d’affecter une valeur) on utilisera
l’opérateur "égal à" (*=*) :

.. code-block:: vala

   int nombre;

   nombre = 30;


Notre variable *nombre* possède désormais l’entier numérique *30* comme valeur.

L’initialisation d’une variable peut également se faire au même moment que sa
déclaration. Ainsi, on pourra remplacer le code précédent par :

.. code-block:: vala

   int nombre = 30;

.. note::
   Nous ne recommandons pas cette façon de faire, nous reparlerons de la
   norme dans un autre chapitre.

Nous pouvons à tout moment demander la valeur contenue dans la variable
*nombre_entier*, par
exemple :

.. code-block:: vala

   int nombre_entier = 10;
   print("%d \n", nombre); // Affiche 10 dans la console.


.. note::
   Les caractères *%d* sont la pour indiquer que *nombre* est un chiffre entier
   décimal.

   Les caractères *\n*, eux, indiquent à la console de faire un saut de ligne.
   Nous en reparlerons dans un chapitre plus en détails sur la lecture/écriture.

La norme des noms
-----------------

Vous pouvez nommer vos variables à peu près n’importe comment, à quelques
détails près. Les noms de variables ne peuvent pas avoir le même nom qu’un type.
Il sera alors impossible d’appeler une variable *int*.

Il est également impossible d’utiliser des caractères spéciaux, comme des
espaces, des tirets, des lettres accentuées ou des caractères de ponctuation.

De même, on ne pourra pas nommer une variable en commençant par des chiffres.

.. note::
   Il est souvent recommandé de nommer ses variables en anglais (langue
   qui ne contient pas d'accent). Vous aurez noté que je ne le fais pas
   volontairement dans ce tutoriel afin de ne pas rajouter une contrainte
   supplémentaire lors de la lecture du code. Mais libre à vous de le faire.

En général, une variable commence par une minuscule et si son nom représente
plusieurs mots, on les séparera par des "underscore" à savoir ces caractères
la : "_" (Sans les guillemets) .
Celui qui le nommera par "tiret du bas" se fera lyncher par ses collèges.
Exemple :


.. code-block:: vala

   int age_du_visiteur;


.. important::

   A noter un détail qui peut paraître évident, mais toutes les variables sont
   réinitialisées à chaque nouvelle exécution du programme. Dès qu’on démarre le
   programme, l'emplacement de mémoire vive est vidé, comme si on emménageait dans des
   nouveaux locaux à chaque fois.

   Il est donc impossible de faire persister une information entre deux
   exécutions du programme en utilisant des variables normales. Pour ceci, on utilisera
   d’autres solutions, comme enregistrer des valeurs dans un fichier ou dans une
   base de données. Nous y reviendrons ultérieurement.

Affectations, opérations, concaténation
=======================================

Nous allons voir comment intéragir avec les variable.
Nous pouvons également faire des opérations *+*, *``*``*, */* ou encore *-*,
par exemple :

.. code-block:: vala

   int resultat = 2 * 3;

ou encore :

.. code-block:: vala

   int age1 = 20;
   int age2 = 30;
   int moyenne = (age1 + age2) / 2;



Vous aurez donc surement deviné que la variable *resultat* contient 6 et que
la moyenne vaut 25.

Il est à noter que les variables contiennent une valeur qui ne peut évoluer
qu’en affectant une nouvelle valeur à cette variable.

Ainsi, si j’ai le code suivant :

.. code-block:: vala

   int age1 = 20;
   int age2 = 30;
   int moyenne = (age1 + age2) / 2;
   age2 = 40;


Les initialisations de variable auront toujours la même valeur définie,
les calculs dans le programme ne seront pas sauvegardé.

Concaténation
-------------

D’autres opérateurs particuliers, que nous ne trouvons pas dans les
cours de mathématiques, existent. Par exemple, l’opérateur ++ qui permet de réaliser une
**incrémentation** de 1, ou l’opérateur -- qui permet de faire une **décrémentation**
de 1.

Une incrémentation de 1 revient à faire ``x = x + 1;`` 
Une décrémentation de 1 revient à faire ``x = x - 1;`` 

De même, les opérateurs que nous avons déjà vus peuvent se cumuler à l’opérateur
pour simplifier une opération qui prend une variable comme opérande et
cette même variable comme résultat.

Par exemple :

.. code-block:: vala

   int age = 20;
   age = age + 10; // age contient 30 (addition)
   age++; // age contient 31 (incrémentation de 1)
   age--; // age contient 30 (décrémentation de 1)
   age += 10; // équivalent à age = age + 10 (age contient 40)
   age /= 2; // équivalent à age = age / 2 => (age contient 20)

Notion de math
==============

Comme nous avons pu le voir dans nos cours de mathématiques, il est possible de
grouper des opérations avec des parenthèses pour agir sur leurs priorités.

Ainsi, l’instruction précédemment vue :

.. code-block:: vala

   int moyenne = (age1 + age2) / 2;

effectue bien la somme des deux âges avant de les diviser par 2, car les
parenthèses sont prioritaires.

Cependant, l’instruction suivante :

.. code-block:: vala

   int moyenne = int moyenne = age1 + age2 / 2;

aurait commencé par diviser l’age2 par 2 et aurait ajouté l’age1, ce qui
n’aurait plus rien à voir avec une moyenne.

En effet, la division est prioritaire par rapport à l’addition.

.. important::
   Attention, la division ici est un peu particulière.

Prenons cet exemple :

.. code-block:: vala

   int moyenne = 5 / 2;
   print("%d \n", moyenne);

Si nous l'exécutons, nous voyons que moyenne vaut 2.

.. hint::
   2 ? Si je me rappelle bien de mes cours de math ... N'est-ce pas plutôt 2.5 ?

Oui et non.

Si nous divisions 5 par 2, nous obtenons bien 2.5.

Par contre, ici nous divisons l'entier 5 par l'entier 2 et nous stockons le
résultat dans l'entier moyenne.

Le Vala réalise en fait une division entière, c'est-à-dire qu'il prend la partie
entière de 2.5, c'est-à-dire 2.

De plus, l'entier moyenne est incapable de stocker une valeur contenant des
chiffres après la virgule. Il ne prendrait que la partie entière.

Pour avoir 2.5, il faudrait utiliser le code suivant :

.. code-block:: vala

   double moyenne = 5.0 / 2.0;
   print("%f \n", moyenne);

Ici, nous divisons deux « doubles » entre eux et nous stockons le résultat
dans un « double ». (Rappelez-vous, le type de données « double » permet de
stocker des nombres à virgule.)

.. note::
   Le Vala comprend qu'il s'agit de double car nous avons ajouté un .0 derrière.
   Sans ça, il considère que les chiffres sont des entiers.

Les caractères spéciaux dans les chaines de caractères
======================================================

En ce qui concerne l’affectation de chaînes de caractères, vous risquez
d’avoir des surprises si vous tentez de mettre des caractères spéciaux dans
des variables de type string.

En effet, une chaîne de caractères étant délimitée par des guillemets " ",
comment faire pour que notre chaîne de caractères puisse contenir des guillemets ?

C’est là qu’intervient le caractère spécial \ (backslash) qui sera à mettre juste devant le
guillemet, par exemple le code suivant :

.. code-block:: vala

   string phrase = "Mon prénom est \"Nicolas\" \n";
   stdout.printf(phrase);

affichera :

.. code-block:: text

   Mon prénom est "Nicolas"

.. important::
    Ici nous n'utilisons pas l'instruction print() mais stdout.printf(), tout simplement car en Vala,
    il n'est pas possible d'afficher des accents avec l'instruction print(), ici le "é" de prénom.

Si vous avez testé par vous-même, vous avez pu remarquer que le caractère
spécial *\n* effectue un saut de ligne.

Ainsi, le code suivant :

.. code-block:: vala

   string phrase = "Mon prénom est \"Nicolas\"\n";
   stdout.printf(phrase);
   print("Passage\nà\nla\nligne\n");

affichera:


.. code-block:: text

   Mon prénom est "Nicolas"
   Passage
   à
   la
   ligne

où nous remarquons bien les divers passages à la ligne.

On peut aussi utiliser le caractère spécial *\t* pour effectuer une tabulation.
Le code suivant:

.. code-block:: vala

   print("Choses à faire :");
   print("\t - Arroser les plantes");
   print("\t - Laver la voiture");

permettra d’afficher des tabulations, comme illustré ci-dessous :

.. code-block:: text

   Choses à faire :
           - Arroser les plantes
           - Laver la voiture

Nous avons vu que le caractère "backslash" était un caractère spécial et qu’il permettait
de dire au compilateur que nous voulions l’utiliser combiné à la valeur qui le
suit, permettant d’avoir une tabulation ou un retour à la ligne.

Comment pourrons-nous avoir une chaîne de caractères qui contienne ce fameux
caractère ?

Le principe est le même, il suffira de faire suivre ce fameux caractère spécial
de lui-même. Exemple:

.. code-block:: vala

   print("Le caractère backslash \\");

En résumé
=========

- Une variable est une zone mémoire permettant de stocker une valeur d'un type
  particulier.
- Le Vala possède plein de types prédéfinis, comme les entiers (int), les
  chaînes de caractères (string), etc.
- On utilise l'opérateur = pour affecter une valeur à une variable.
- Il est possible de faire des opérations entre les variables.
