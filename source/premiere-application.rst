*********************
Première application
*********************

De retour dans notre dossier Projects, on crée un sous-dossier hello-world

.. code-block:: bash

   $ mkdir hello-world

Puis dedans on crée un autre dossier pour notre nouvelle application.

.. code-block:: bash

   $ cd hello-world
   $ mkdir hello-again

Créeons le dossier src puis éditons notre nouveau fichier hello-again.vala

.. code-block:: bash
   
   $ cd hello-again
   $ mkdir src
   $ cd src
   $ scratch-text-editor hello-again.vala

Nous allons écrire un entête pour le copyright comme pour une vraie application :

.. code-block:: bash
   :linenos:

   /***
    Copyright © 2014 Votre nom <email@example.com>

    This file is part of Hello Again.

    Hello Again is free software: you can redistribute it and/or
    modify it under the terms of the GNU General Public License as published
    by the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    Hello Again is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with Hello Again. If not, see <http://www.gnu.org/licenses/>.
   ***/
    
Cette fois on reprend la même structure de base que gtk-hello.vala mais on vas juste mettre un
Gtk.Label au lieu d'un Gtk.Button

.. code-block:: vala

   var label = new Gtk.Label ("Hello Again World!");

Et pensez à l'ajouter à votre fenêtre ! Donc si vous avez pigé, vous avez déjà écris window.add
(label);

Si vous avez fait comme il fallait, vous devriez avoir ceci :

.. code-block:: vala
   :linenos:

   /***
    Copyright © 2014 Votre nom <email@example.com>

    This file is part of Hello Again.

    Hello Again is free software: you can redistribute it and/or
    modify it under the terms of the GNU General Public License as published
    by the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    Hello Again is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with Hello Again. If not, see <http://www.gnu.org/licenses/>.
   ***/

   int main (string[] args) {
       Gtk.init (ref args);

       var window = new Gtk.Window ();
       window.title = "Hello World!"
       window.set_border_width (12);
       window.set_position(Gtk.WindowPosition.CENTER);
       window.set_default_size (350, 70);
       window.destroy.connect (Gtk.main_quit);

       var label = new Gtk.Label ("Hello Again World!);

       window.add(label);
       window.show_all ();

       Gtk.main ();
       return 0;
   }

Compiler l'appli et testez là !

.. code-block:: bash

   $ valac --pkg gtk+-3.0 hello-again.vala
   $ ./hello-again

Tadaa !

.. figure:: _static/premiere-application/gtk-hello-again.png
    :align: center
