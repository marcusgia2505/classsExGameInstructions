.. _develop:

======================
Develop your own games
======================

To develop your own games change to the editing |pic_editmode|. In the editing mode, you can create games according to your own needs. Games can be clicked together with an easy-to-use modular backend system. You divide your game in stages and you can add different elements (input, output, calculation,...) for your games.

	.. note:: In the editing mode, changes are stored automatically. If you change your an element of your game and click next to the element, the element is stored. Most of the elements blink green when they are stored. 

	.. note:: If a game has already been played by at least 10 participants, it cannot be adapted any more. The same applies if the game was created by another person. You can, however, copy the game and then adapt it.

.. |pic_editmode| image:: _static/pic/editMode.png
   :width: 15px

Top bar in the editing mode
============================

The top bar in the editing mode looks like this:

.. image:: _static/Leiste.JPG
    :alt:  300px

It provides you with several options which are described below.

Select game
~~~~~~~~~~~~

.. image:: _static/Selectgame.JPG
    :alt:  300px

Click on the button in the left corner to open the drop down list of your existing games. Clicking on a game will open the selected game in the editing mode. If you open the editing mode, the currently running game is preselected.


Game
~~~~~

By clicking on *game*, a dropdown menu will open, which shows up to four possible options. The number of options is reduced if you do not own the game. Then, e.g. you cannot delete the game.

.. image:: _static/Game.JPG
    :alt:  300px

Game settings
--------------
Clicking on game settings, a new screen appears. On this screen you can change different settings of the game. You can also access this screen from the overview by clicking on the |pic_setting| symbol next to the name of a game. Changes to any field are again saved automatically. 

.. image:: _static/game_settings.PNG

Name of the game
	First of all, you can specify the name of the game. If your game is available in different languages, you have to provide a translation of the title as well. 

Alternative title
	You can also define an alternative title which is displayed instead of the name wherever the game is listed in your own account. Other users will see the original name of the game and not the alternative title.

	..note:: This features is useful if you imported a game, which has the same name as one of your games. Then you can use the alternative title to distinguish from your game, because you cannot change the original name of the game which belongs to another user.

Creation date
	The created field shows the creation date of the game, which is not editable. 

Language
	For each game, you can specify a primary language and optionally a second language. If you add a second language all text fields will be shown twice for both languages.

	.. note:: If a text field misses the multi-language feature, you can input the text in both languages separated with $$. E.g. Please decide now$$Bitte entscheide jetzt. 

	.. note:: classEx always chooses automatically which language to use based on the account language. If the game is available in the account language it uses this language. Then it tries to find an English version. Otherwise it displays the available language.

Availability
	You can specify whether you would like a game and its results to be public or not. By default, all games (and their results) are public. You can set a game (and its results) to private or you can set only the results to private and the game to public. In the latter case, other experimenters can still copy your game, but they do not see previous results by you. If you decide to set games or results to public they become subject to a creative commons license as described in the `terms of use`_. You can change the setting of public and private also in the overview by clicking on |pic_private| or |pic_public| next to the name of the game. The option to set only the game public, but results private is not available there.

	If you set your game public, it can be found in the :ref:`Organize:Repository`  and others can play and copy the game. If you set your game private, it is not listed in the repository anymore, but previous made copies of your game will remain with their owners and are not revoked.

Additional libraries
	If you click on *additonal libraries* new settings appear. You can select to load different libraries for the participants. Libraries are packages for special usages. They come with an increased necessity to load data from the server (for each participants). Therefore, you should them only turn on if you need them. For lecturers, they are loaded automatically.  The three available libraries are `plotly`_ or `highcharts`_ for drawing graphs on the participant screen. The library `phaser`_ can be used for creating game-like interactions. For more information visit the respective website of the library by clicking on the library's name.


.. _terms of use: https://classEx.de/TermsOfUse.pdf
.. _plotly: https://plot.ly
.. _highcharts: https://www.highcharts.com
.. _phaser: https://phaser.io


Information on the game
------------------------

Here you can classify your game and provide meta-information on the content. This information can be accessed by other users and provides them with more details on your game. Please provide this information in English.

.. note:: classEx promotes the idea of sharing games. Therefore, it is important to provide meta-information on games so that they can be found easily. Another advantage is that you can transfer your meta-information directly to the data-repository :ref:`Run:Data`.


Keywords
	You can provide a set of keywords to better describe your game. Many standard keywords on typical games are offered automatically when typing in some characters. Keywords are shown in the repository.

Comments
	In the comments section, you can provide a brief description of your game. Comments are shown in the repository and if others import your games to their account, it is shown in their overview.

Credentials
	This field can be used to state a reference or source of your game. This will be shown in the repository and displayed in the lecture mode below the title of the game.



	.. |pic_setting| image:: _static/pic/setting.png
                            :width: 15px
	.. |pic_public| image:: _static/pic/public.png
							:width: 15px
	.. |pic_private| image:: _static/pic/private.png
							:width: 15px

Copy game
----------
If you click on *copy game*, the currently selected game is copied and can then be edited and adapted. 


.. note:: The difference between copying and importing is that with the latter classEx only sets a reference to the original game. Therefore, it cannot be modified, but only used. A copied game, instead, is a complete copy of the original game and can be changed.

Delete game
------------
By clicking on *delete game*, the currently selected game is deleted. For your safety, you will be asked if you really want to delete the game. It is not possible to delete the game if it has already been started in the lecture mode. You then need to start a different game in the lecture mode before being able to delete the selected one. You cannot undo the deletion of a game.

.. note:: If it happens that you accidentally delete a game, please email to classEx@uni-passau.de as soon as possible. Internally, we completely remove deleted games only each month so that recovery is possible.

New game
---------
This creates a new game. A standard new game is always a single-choice question with four possible answers. Before you can edit the game, classEx takes you to the :ref:`Develop:Game setting`_ of the created game were you have to provide a title.  You have to select a language and to choose whether the game should be public or private. Once you are done, click on *save* to create the game. classEx automatically takes you to editing mode where you can proceed designing the game.


Parameter
~~~~~~~~~~
If you click on parameters, you can edit the parameters of a game. Parameters are global variables that can be changed right before starting a game. They allow other lecturers to run your game without changing the implementation of the game. More information can be found under :ref:`Develop:Parameters`.


Test a game
============

Before actually using a game in your lecture or while you develop, you can always test a game. To do so switch to the lecture mode and select your game, if it is not selected yet. 

Next, open as many test participant as you need for testing your game by clicking on the *add test participant* icon |pic_testparticipant|. This opens a participant screen in a new tab. You will see the game just as your subjects will see it when actually playing the game. You can open as many test participants as you want, which enables you to also test interaction between participants.

.. note:: You can open multiply test participants by holing the Ctrl-Key and clicking multiple times on the test participant icon |pic_testparticipant|. 

Then start your game. You can perform the interaction required in the browser tabs for each participant and can see how your game is running. 

.. note:: Test participants are not reload-safe. This means that if you reload the page, in some cases the content of the page may change. Real participants cannot do this.

If something is not working, go back to the editing mode and check your settings there. If you used variables and programs, you can use the :ref:`Programming:Diagnosis tool` for error spotting. The diagnosis mode shows all available variables and helps to debug them.


.. note:: All major browsers also provide their own development tools which can be very helpful for error spotting. They provide a console which gives feedback on potential errors. In this console, you can also observe the background task performed by classEx and if they are running correctly. Finally it allows you to see javascript errors. In Firefox, the development tools are started by hitting F12.

.. |pic_testparticipant| image:: _static/pic/addPlayer.png
   :width: 15px





Define stages
==============

Stages are points of synchronisation in a game. Synchronization means that for the next stage to begin, all elements of the previous stage must have been finalized. Generally, the input phase is one stage and the results or output phase is a different stage, as the output can only be displayed after all participants have entered their input. Each stage consists of one or more elements. Stages are ordered in tabs in a horizontal way in classEx. The first tab is not a stage before shows the options for assignment of roles and groups. 

.. image:: _static/Stage.PNG
    :alt:  300px

    In the [[editing Mode]], you can choose to give the stages names instead if numbers in order to identify them more easily. To give them a name, simply enter it in the box.


Rounds
~~~~~~

If you want to run one or more stages more than once, you can define rounds and determine how often you would like to return to a certain stage. If you determine the return value as 0 or if the stage has been run for the predetermined number of times, classEx will redirect you to the next stage right underneath. You can also determine which stage you want to return to if you play several rounds.

Late arrival
~~~~~~~~~~~~

You can specify whether participants can arrive late, i.e. if they only just logged in. You can choose for this to be possible, not possible, or only possible in the first round.

Move stages
~~~~~~~~~~~

When you create a new stage, this stage will automatically be defined as the next stage. You can move stages by pressing *Move stage upwards* or *Move stage downwards*. The order in which stages are run is always from left to right.

Add stage
~~~~~~~~~

You can add a new stage by clicking on *Add new stage* beside the tabs displaying the different stages or on the top right of the current stage.

Delete stage
~~~~~~~~~~~~~
You can delete a stage by pressing *Delete stage*.





Assignment and Matching
=======================

Left to the tab *stage 1* you find the tab *assignment and matching*. Here, you can specify whether you want to assign participants to treatments, groups, roles or a combination of all (complex assignment). 

.. image:: _static/Matching.PNG
    :alt:  300px

Assignment at the beginning of a game
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

classEx allows you to flexibly adapt to an unknown number of participants, meaning that you choose the number of different roles, the number of treatments and the size of groups. ClassEx then assigns participants automatically. Specifically, have following available options:

No assigment
	Participants all are assigned to role 0, treatment 0 and group 0.

treatments
	Allows you to assign participants to treatments. A division into treatments will distribute participants evenly over treatments. You can select any number of treatments between 1 and 10. Treatments will be distributed according to arrival in the experiment (e.g. with two treatments the first will be treatment 1, the second treatment 2, the third again treatment 1,...)

role and group
	Allows you to assign participants to a number of different roles in the game. Participants will be allocated to role 1, role 2, role 3... alternately. Participants will also be assigned to a group. E.g. if you have defined 3 roles, a group will consists of role 1, role 2 and role3. If you want to have groups with asymmetric combination of roles please use complex assignment.

group
	Allows you to assign participants to groups (all participants will have the same role). Groups are filled one after each other. You are free to select any group size. 

treatment + role and group
	Allows you to assign both role+group and treatments. If combines the two above options.

complex assignment
	Allows you to assign participants to a different number of roles, treatments and groups.


	Hint: The so-called between-subject design examines how a controlled variation of the game influences the behaviour of different participants. This can be implemented using treatments. The groups in one treatment only interact with participants in their own treatment and never with participants of the other treatment. The game can be adapted for every treatment, for example by providing different information, altered probabilities of random events or diverse strategic interactions.</div>

Matching
--------

If you have assigned participants, you can specify how you want them to be rematched if your game consists of several rounds. You can choose from the following options:

partner
	Participants stay in the same groups and keep their roles throughout the entire game.

random
	Participants are randomly assigned to a new role, group and treatment (if specified).

Absolute stranger matching, ensuring that participants never interact with participants they have interacted with before, is not available.

Random matching with constant roles
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Random matching with constant roles means randomly matching the subjects into new groups at the beginning of each round but at the same time keeping the subject's roles constant. This is not provided as an option but can be implemented manually as follows.

1. The assignment selected must be "role and group". The matching method selected should be "partner".

2. You need to add a globals program and a subjects program in the first repeated stage of your experiment.

3. Insert the following code in the globals program:

.. code:: php

	$rolesarray = $getRoles();
	# Shuffle rolesarray
	$keys = array_keys($rolesarray);
	shuffle($keys);
	foreach($keys as $key) { #Note that $key are the values!!!
	$new[$key] = $rolesarray[$key];
	}
	$rolesarray = $new; #$rolesarray is now shuffled but with the initial key-value pairs
	# Create new groups
	$numberofroles = max($rolesarray);
	for ($i = 1; $i <= $numberofroles; $i++) {
  	$count[$i] = 1; #Initializing group count per role array
	}
	foreach ($rolesarray as $key => $values){ #Looks at every subject in new (shuffled) order
  	for ($i = 1; $i <= $numberofroles; $i++) { #Tries every role
    	if ($values == $i) { #If role fits
    	${"group_$key"} = $count[$i]; #Group assignment to group count
    	$count[$i] = $count[$i]+1; #Increase group count for the role
	}}}

4. Insert the following code in the subjects program:

	$save("group", ${"group_$id"}); #saves the value of the "group_[id]" variable created in the globals program as new value of "group"

Further settings
----------------

On the page assignment and matching you can further choose if the role should be displayed in the header of the participants page and if the participant id should be displayed there as well.

Available roles
---------------

Up to 13 roles are available (and an additional gray role 0 for no role assignment). Role 2 is distinguishable by a different figure to allow distinction for person who have red–green color blindness.

.. image:: _static/Allroles.PNG
    :alt:  300px

This roles are standardized items and are shown in the header of the participant's page.

Elements (display condition,…, mit Bsp…, general input)
===========================================================

Elements are the modules of a stage. A stage has two areas in which you can add modules: participants and lecturer.

.. image:: _static/Stage.PNG
    :alt:  300px
    
The left side represents the participant level (subject level). Visual elements added here are displayed on the participants' devices. Program code (subjects) added here is run for every single participant.
The right side represents the lecturer level (global level). Visual elements added here are displayed on the lecturer's screen. Program code (globals) added here is run once for all participants.

You can chose from text elements, input elements (numerical input, likert scales, …), programme elements and output elements (histograms, bar charts, …). These can be combined and arranged as you like.

	Hint: Input and output elements should be located in different stages in order to collect all input in the first stage. Then, the lecturer can synchronise the game and turn to the output elements in the next stage.

Adding elements
================

You can add an element via clicking on *add element* and selecting the type of element you want to add. After that you have to choose where you want to place the element. If you do so the following two icons will appear for every possible location of the element.

.. image:: _static/Pasteelement.PNG
    :alt:  300px

Choose a location for your element by clicking on the corresponding *paste element* icon or cancel placing the icon by clicking on any *do not paste* icon. Keep in mind that the order of emlements defines how the elements are displayed on the participants' devices.

Handling elements
==================

.. image:: _static/Elements.PNG
    :alt:  300px

Element Number
	The elements are numbered (E1, E2, …). This also defines the order of display in a stage. Elements can be moved within a stage with the *move element* arrows.

Element Type and Help
	Beside the number of the element, you can see the element type. Clicking on the info button next to the element type leads you to the respective description in this documentation.

Groups, Treatments and Roles
	If you have defined groups, treatments or roles, you can also choose whether the element shall be displayed for all groups, treatments or roles.

Delete Element
	You can delete the element by pressing *delete element*.

Copy Element
	You can copy an element by pressing *copy element*

Cut and Paste
	You can cut and paste an element by pressing *cut element*.

Display Condition
	If showing the element should be contitional (e.g. not for every role or dependent on other variables) you can specify the display condition for an element in the code line that appears when you click on *show display condition*.



Parameters
==========

Parameters are global variables that can be adjusted in the lecture mode. You can define parameters to enable adaptation of the game for lecturers without any knowledge of how to edit games. You can then play the same game several times with different parameters.

You can define parameters by clicking on the *parameter* button in the top bar of the editing mode. Here you can see all defined parameters for the active game, edit them and add new ones. After adding a parameter you can use it as global variable in elements., you can set different parameters of a game that can be changed easily in the lecture mode 

Here is an example for a public goods game:

.. image:: _static/Parameter.JPG
    :alt:  300p

Languages 
=========

For some elements, you can enter the text in two different languages, English and German.

.. image:: _static/Language.PNG
    :alt:  300p

To switch the languages on and off, you can click on the flag symbols next to the game name.

.. image:: _static/Languageonoff.PNG
    :alt:  300p

For other elements, this function has not been implemented yet. In this case, you need to enter both languages in one text box, separated by $$, for more information see `Text Box`_. 

Identification of subjects in the system
========================================

By default, subjects are completely anonymous in classEx. Should it be required, you also have several possibilities to identify subjects in the system.

Ticket: You can provide participants with a personalised ticket to log in to classEx. This way you can ensure that participants only take part on one device and also track the actions of specific participants. You simply need to add &tic= to the URL. The ticket is saved to the participant data and can be retrieved as $tic; in the game.

Ask for data during the game: At a certain stage, or after the end of the game, you can ask participants to enter their personal data or an ID you provide them with.

During login: You can change the settings so that participants are asked for certain data before they log in. For this, go to "course data" and click on additional settings. You can then enter what you would like participants to enter before logging in.

Here is an example:

.. image:: _static/Data1.PNG
    :alt:  300px
    
And this is what it looks like for participants before logging in:

.. image:: _static/Data2.PNG
    :alt:  300px

