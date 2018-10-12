===========================================
Tutorial: How to develop a simple game
===========================================

To help you getting started with creating your own games this section gives step by step instructions for how to implement an Ultimatum Game.

The Ultimatum Game
==================

In an Ultimatum Game the participants play in groups of two. One of them takes the role of the proposer. He decides upon how to divide an initial endowment between him and the other participant – the responder. The responder then decides whether he accepts the proposal. If he does so, the final payoffs of the participants are according to the proposal. If the responder does not accept the proposal both participants receive nothing as final payoff.

Building the game
==================
To create a new game click on "new game" in your overview screen. Type in a game name of your choice and change the availability to “private”. Thus other users cannot see “your” Ultimatum Game. Click “save”. ClassEx will automatically switch into editing mode and you can start building the game.

Matching
~~~~~~~~

Go to the tab “matching”. Select “role” in the drop-down menu “matching” and select “2” in the drop-down menu “roles”. This means the participants in this game are selected into groups of two with every group consisting of one participant of each role.

Stage 1: Proposer’s decision
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Go on to the tab "stage 1". In this first stage of the game the instructions for all participants should be on the lecturer’s screen (all participants can see it) and the proposers should decide how much they want to transfer to the responder. The stage should be started by the lecturer pressing a start button.

First type in a name for the stage, e. g. “UltimatumProposer”. “Late arrival” should be “possible”. That means, participants can still log in after the stage has been started by the lecturer. The start button is already implemented by default in the first stage in the lecturer field on the right side.

To add the instructions click on “add new element” in the lecturer field and select “text box”. Click on the little symbol Insert.png above the start button field to insert the instructions above the start button. Insert the game instructions that should be visible for all participants into this text box.

Than you have to edit the participant’s field on the left side. An input element with one input field is implemented by default. Change the “Type of input field” to “Numeric input field”. Every participant in the role of a proposer will be able to decide upon the amount he wants to keep for himself by entering it into this field. The field “variable names” next to the “Type of input field” defines the variable name. This is the internal name of the variable and will not be visible for the participant. Type in e. g. “keep”. Only the proposers should have an input field in this stage. Therefore change the field “for all roles” to “only role 1”. In the text field you can insert a description of the input value that is visible for the participant. Type in e. g. “For me:”. Below the text field you can edit some more settings of the input field. The “Minimum” should be "0" because the responder cannot keep a negative amount. The “Maximum” should equal the initial endowment because the proposer cannot keep more than this for himself. The initial endowment could be a parameter you maybe will want to change in the future. You should only need to change one value to do so. Therefore you should define the initial endowment as a general parameter of the game. To do so you need to add a “program code (subjects)” element (participants field -> add new element -> program code (subjects)). Click on the little symbol Insert.png above the input field to insert the program field. In the program field you now can define the initial endowment as a variable. Type in “$endow = 10;” for an initial andowment of 10. Now you can use this variable to define the upper threshold of the amount the proposer can keep. Type “$endow;” in to the “Maximum” field. Type in “0” into “decimal place” to not allow for decimal numbers and define the "unit" e. g. as “€”.

To make sure the proposer fully understands his decision the value left for the responder should be calculated and displayed. Therefore click on Insert.png to add a new input field in the input element. Change the field “for all roles” to “only role 1” again and name the variable (e. g. “send”). Isert the description for the variable in the text box, e. g. “participant 2 gets:”. You don’t need minimum and maximum values because the value should be calculated automatically from the variables "keep" and "endow". Set decimal place and unit the same as in the first input field. Because this field is actually not an input field in which the participant can insert a value check the box “output only”. To calculate the updated amount for the respondent every time the proposer changes the value he wants to keep you need to insert a third input field in your input element. This time it the “Type of input field” is “calculation field”. Again change the field “for all roles” to “only role 1”. Type “send=endow-keep;” into the program field.

For clarification you should add a more general explanation of the stage for the proposers that is displayed above the input element. Click on “add new element” in the participants field and select “text box”. Click on Insert.png between the “program code (subject)” and the input element. Again change the field “for all roles” to “only role 1”. Then insert the instructions, e. g. “You decide how to divide $endow; € between you and participant 2 . participant 2 decides, if he accepts or rejects. If he rejects, you both get nothing.”

Stage 2: Responder’s decision
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In the second stage the responders are informed about the proposals and they decide whether to accept or to reject.

To create a new stage click on Plus.JPG on the right side of the tab of stage 1 (now bearing the name you chose). Type in a name for stage 2 (e. g. "UltimatumResponder"). “Late arrival” should be “not possible” in this stage, because the matching is already done and newcomers cannot be integrated once the first stage has been played. The new stage has by default implemented a textbox in the participant’s field. Use this textbox to inform the responder about the proposal. You need to display for every responder the values of the proposal made by the proposer who was matched to them. To do so you need a "program code (subjects)" field again. Insert it above the text box and change “for all roles” to “only role 2”. Type in the following code:

	| $keep = $findVariablePartner(“keep”;$round);
	| $send=$endow-$keep;

The first line defines a variable “keep” and assigns to it the value of the participant’s matching partner’s “keep”-variable. The second line calculates how much the proposer kept for himself and assigns the value to a variable “send”. Now you can use both new variables to inform the responder about the proposal made to him. Change “for all roles” to “only role 2” in the text box and type in the following instructions:

	"participant 1 has decided to split $endow; as follows: $keep; for participant 1 and $send; for you. You can accept the proposal 		or reject it. If you reject it, both get nothing."

Now you need an input element via which the responder can accept or reject the proposal. Insert an input element beneath the text box and insert a “new input field” within the input element. Change the type to “Buttons (Single Choice)”. Set the variable name to e. g. “accepted” and define the Input field as visible for “only role 2”. Write a text into the text box that should appear above the “accept” and “reject” button (e. g. “Your decision”). To insert these buttons type “2” into the text field next to “add new possible answer” and click on Plus.JPG. Insert “Accept” and “Reject” into the text fields. The values assigned to the decision buttons are very important. Choose the value “1” for the accept button and the value “0” for the reject button.

The second stage should start for a responder automatically as soon as “his” proposer has sent a proposal. Therefore delete the “start button” field in the lecturer field by clicking on Rubbish.JPG. Then insert an “automatic start” via “add new element”. Change the mode to “wait for others”. To display how many proposers and responders have already made their decisions on the lecturer’s screen, set the counter to “display” and the count to “by role”.

Stage 3: Results
~~~~~~~~~~~~~~~~~

When the responders have accepted or rejected the proposals you can display the results in a third stage. Add a new stage and name it e. g. “Results”. “Late arrival” again is “Not possible”. The two fields next to the “late arrival” field define how often and where to jump after finishing this stage. You can define the number of rounds you want to play. Choose “back to stage 1” and e. g. “2x” (for playing two rounds).

For both participants the payoff depends on whether the responder accepted the proposal or not. You have to distinguish these two cases. To do so you use a program code (subjects) field again. You need one for “only role 1” and one for “only role 2”. The program for role 1 is:
	
	| $accepted=$findVariablePartner(“accepted);
	| $payoff=$keep*$accepted;
	| if($accepted==0) {
	| $text=”participant 2 has rejected your proposal.”
	| } else {
	| $text=”participant 2 has accepted your proposal.”
	| }

The program for role 2 is:

	| $payoff=$send*$accepted;
	| if($accepted==0) {
	| $text=”You have rejected the proposal.”
	| } else {
	| $text=”You have accepted the proposal.”
	| }

Then insert two text boxes in the participants field. Again one for role 1 and one for role 2. In these text boxes you inform the participants about their final payoff. For role 1 the text could be:

	You have proposed to split $endow; as follows: $keep; € for you and $send; € for participant 2. $text; Your payoff is $payoff; €.

For role 2 the text could be:

	participant 1 has proposed to split $endow; as follows: $keep; € for him and $send; € for you. $text; Your payoff is $payoff; €.

In the lecturer field you can show the results. Delete the start button that is implemented in a new stage by default. Then add a results bubble element. Select the variable “accept” for the x-axis with 0 as minimum and 2 as maximum value. Choose a label for the x-axis, e. g. “acceptance." Select the variable “keep” for the y-axis with 0 as minimum and $endow as maximum value. Choose a label for the y-axis, e. g. “proposal (amount kept)”. Select “display if stage is activated and after” and select “by role” in the field “count”.

Testing the game
=================

To test the game, change into lecture mode. You can test the game on your own PC by clicking on Testpart.JPG in the top bar of the lecture mode. This opens a participant screen in a new tab. You will see the game just as your subjects will see it when actually playing the game. You can open as many screens as you want, where each screen represents a participant. After opening enough test participant screens click "Start" in the lecturer screen. Then you can go through the game with all test participants. 

======================
Develop your own games
======================

To develope your own games change to the editing mode. The top bar in this mode looks like this:

.. image:: _static/Leiste.JPG
    :alt:  300px

It provide you with several options which are described below.

	Hint: If you make any input in the editing mode and leave the input field the value is stored automatically.
Select game

.. image:: _static/Selectgame.JPG
    :alt:  300px

Click on the button in the left corner to open the drop down list of your existing games. Clicking on a game will open the selected game.

If a game has already been played by at least 10 participants, it cannot be adapted any more. The same applies if the game was created by another person. You can, however, replicate the game and then adapt it.

.. image:: _static/Alreadyplayed.JPG
    :alt:  300px

By clicking on the button game a drop down menu opens.

.. image:: _static/Game.JPG
    :alt:  300px

Game settings
	Clicking on game settings lets you change the name of the game and lets you specify whether you would like it to be public or not. By default, all games are public. This function is also available in the Overview on the Starting Screen. Also, you can provide additional information on your game. You can classify your game and provide information on the content and additional comments. This information can be accessed by other users and provides them with more details on your game.

Copy game
	The currently selected game is copied and can then be edited and adapted.

Delete game
	By pressing "delete game", the currently selected game is deleted. For your safety, you will be asked if you really want to delete the game. It is not possible to delete the game if it has already been started in the lecture mode. You then need to start a different game in the lecture mode before being able to delete the selected one. You cannot undo the deletion of a game.

New game
	Creates a new game. A standard new game is always a single-choice question with four possible answers. Find an example of such a single-choice question here.


Test a game
============

Before playing a game in your lecture, you can test the game. To do so switch to the lecture mode and select your game. Selecting your game is not necessary if it is the active game in the lecture mode already. Next, open as many test participant as you need for testing your game by clicking on the *add test participant* icon.

.. image:: _static/Addparticipant.PNG
    :alt:  300p

This opens a participant screen in a new tab. You will see the game just as your subjects will see it when actually playing the game. You can open as many screens as you want, which enables you to also test interaction between participants in games with several roles.

Then start your game. You can perform the interaction required in the browser tabs for each participant.

If something is not working or an error occurs you can use the diagnosis mode for error spotting.




Create a new game
=================

To create a new game you can either click on *new game* in you Overview or go to editing mode and select *game - new game*.

.. image:: _static/Settings.PNG
    :alt:  300px

classEx takes you to the settings page of the created game were you have to select a name. You can also define an alternative name which is displayed instead of the name wherever the game is listed. You have to select a language and can define a second language that is used if the account language is set to this language. Also you have to choose whether the game should be public or private.
Further you can insert information on the game in the left column. You can select keywords, add comments and credentials. The credentials are typically used for references to published literature relevant for your game. The credentials will be displayed next to the name of you game. 
Once you are done click on *save* to create the game. classEx automatically takes you to editing mode where you can proceed designing the game.

Assignment and Matching
=======================

Left to the tab *stage 1* you find the tab *assignment and matching*. Here, you can specify whether you want to assign participants to treatments, groups, roles or a combination of all (complex assigment). 

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

	| $rolesarray = $getRoles();
	| # Shuffle rolesarray
	| $keys = array_keys($rolesarray);
	| shuffle($keys);
	| foreach($keys as $key) { #Note that $key are the values!!!
	| $new[$key] = $rolesarray[$key];
	| }
	| $rolesarray = $new; #$rolesarray is now shuffled but with the initial key-value pairs
	| # Create new groups
	| $numberofroles = max($rolesarray);
	| for ($i = 1; $i <= $numberofroles; $i++) {
  	| $count[$i] = 1; #Initializing group count per role array
	| }
	| foreach ($rolesarray as $key => $values){ #Looks at every subject in new (shuffled) order
  	| for ($i = 1; $i <= $numberofroles; $i++) { #Tries every role
    	| if ($values == $i) { #If role fits
    	| ${"group_$key"} = $count[$i]; #Group assignment to group count
    	| $count[$i] = $count[$i]+1; #Increase group count for the role
	| }}}

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

Define your stages
==================

Games consist of several stages. There are at least 2 stages, one for the decision input and one for the result output. Stages are ordered sequentially and are meant to be synchronization points in the game. Synchronization means that for the next stage to begin, all elements of the previous stage must have been finalized.

Configuration of Stages
~~~~~~~~~~~~~~~~~~~~~~~~

Stages are points of synchronisation in a [[Games|game]]. Generally, the input phase is one stage and the results or output phase is a different stage, as the output can only be displayed after all [[Participants|participants]] have entered their input. Each stage consists of one or more [[Elements|elements]] (e.g. input, results, small programmes) that require the input of at least one participant. In the [[editing Mode]], you can choose to give the stages names instead if numbers in order to identify them more easily. To give them a name, simply enter it in the box.

.. image:: _static/Stage.PNG
    :alt:  300px

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

Ticket: You can provide participants with a personalised ticket to log-in to classEx. This way you can ensure that participants only take part on one device and also track the actions of specific participants. You simply need to add &tic= to the URL. The ticket is saved to the participant data and can be retrieved as $tic; in the game.

Ask for data during the game: At a certain stage, or after the end of the game, you can ask participants to enter their personal data or an ID you provide them with.

During login: You can change the settings so that participants are asked for certain data before they log-in. For this, go to "course data" and click on additional settings. You can then enter what you would like participants to enter before logging in.

Here is an example:

.. image:: _static/Data1.PNG
    :alt:  300px
    
And this is what it looks like for participants before login:

.. image:: _static/Data2.PNG
    :alt:  300px

