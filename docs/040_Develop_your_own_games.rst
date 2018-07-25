=====================
Develop you own games
=====================

Tutorial: Exemplified instructions to program an ultimatum game
===============================================================

To help you getting started with creating your own games you find instructions for how to implement an Ultimatum Game in classEx here.
Contents

    1 The Ultimatum Game
    2 Building the game
        2.1 Matching
        2.2 Stage 1: Proposer’s decision
        2.3 Stage 2: Responder’s decision
        2.4 Stage 3: Results
    3 Testing the game

The Ultimatum Game

In an Ultimatum Game the participants play in groups of two. One of them takes the role of the proposer. He decides upon how to divide an initial endowment between him and the other player – the responder. The responder then decides whether he accepts the proposal. If he does so, the final payoffs of the players are according to the proposal. If the responder does not accept the proposal both players receive nothing as final payoff.
Building the game

To create a new game click on "new game" in your overview screen. Type in a game name of your choice and change the availability to “private”. Thus other users cannot see “your” Ultimatum Game. Click “save”. ClassEx will automatically switch into editing mode and you can start building the game.
Matching

Go to the tab “matching”. Select “role” in the drop-down menu “matching” and select “2” in the drop-down menu “roles”. This means the participants in this game are selected into groups of two with every group consisting of one participant of each role.
Stage 1: Proposer’s decision

Go on to the tab "stage 1". In this first stage of the game the instructions for all participants should be on the lecturer’s screen (all participants can see it) and the proposers should decide how much they want to transfer to the responder. The stage should be started by the lecturer pressing a start button.

First type in a name for the stage, e. g. “UltimatumProposer”. “Late arrival” should be “possible”. That means, participants can still log in after the stage has been started by the lecturer. The start button is already implemented by default in the first stage in the lecturer field on the right side.

To add the instructions click on “add new element” in the lecturer field and select “text box”. Click on the little symbol Insert.png above the start button field to insert the instructions above the start button. Insert the game instructions that should be visible for all participants into this text box.

Than you have to edit the participant’s field on the left side. An input element with one input field is implemented by default. Change the “Type of input field” to “Numeric input field”. Every participant in the role of a proposer will be able to decide upon the amount he wants to keep for himself by entering it into this field. The field “variable names” next to the “Type of input field” defines the variable name. This is the internal name of the variable and will not be visible for the participant. Type in e. g. “keep”. Only the proposers should have an input field in this stage. Therefore change the field “for all roles” to “only role 1”. In the text field you can insert a description of the input value that is visible for the participant. Type in e. g. “For me:”. Below the text field you can edit some more settings of the input field. The “Minimum” should be "0" because the responder cannot keep a negative amount. The “Maximum” should equal the initial endowment because the proposer cannot keep more than this for himself. The initial endowment could be a parameter you maybe will want to change in the future. You should only need to change one value to do so. Therefore you should define the initial endowment as a general parameter of the game. To do so you need to add a “program code (subjects)” element (participants field -> add new element -> program code (subjects)). Click on the little symbol Insert.png above the input field to insert the program field. In the program field you now can define the initial endowment as a variable. Type in “$endow = 10;” for an initial andowment of 10. Now you can use this variable to define the upper threshold of the amount the proposer can keep. Type “$endow;” in to the “Maximum” field. Type in “0” into “decimal place” to not allow for decimal numbers and define the "unit" e. g. as “€”.

To make sure the proposer fully understands his decision the value left for the responder should be calculated and displayed. Therefore click on Insert.png to add a new input field in the input element. Change the field “for all roles” to “only role 1” again and name the variable (e. g. “send”). Isert the description for the variable in the text box, e. g. “Player 2 gets:”. You don’t need minimum and maximum values because the value should be calculated automatically from the variables "keep" and "endow". Set decimal place and unit the same as in the first input field. Because this field is actually not an input field in which the participant can insert a value check the box “output only”. To calculate the updated amount for the respondent every time the proposer changes the value he wants to keep you need to insert a third input field in your input element. This time it the “Type of input field” is “calculation field”. Again change the field “for all roles” to “only role 1”. Type “send=endow-keep;” into the program field.

For clarification you should add a more general explanation of the stage for the proposers that is displayed above the input element. Click on “add new element” in the participants field and select “text box”. Click on Insert.png between the “program code (subject)” and the input element. Again change the field “for all roles” to “only role 1”. Then insert the instructions, e. g. “You decide how to divide $endow; € between you and player 2 . Player 2 decides, if he accepts or rejects. If he rejects, you both get nothing.”
Stage 2: Responder’s decision

In the second stage the responders are informed about the proposals and they decide whether to accept or to reject.

To create a new stage click on Plus.JPG on the right side of the tab of stage 1 (now bearing the name you chose). Type in a name for stage 2 (e. g. "UltimatumResponder"). “Late arrival” should be “not possible” in this stage, because the matching is already done and newcomers cannot be integrated once the first stage has been played. The new stage has by default implemented a textbox in the participant’s field. Use this textbox to inform the responder about the proposal. You need to display for every responder the values of the proposal made by the proposer who was matched to them. To do so you need a "program code (subjects)" field again. Insert it above the text box and change “for all roles” to “only role 2”. Type in the following code:

$keep = $findVariablePartner(“keep”;$round);
$send=$endow-$keep;

The first line defines a variable “keep” and assigns to it the value of the player’s matching partner’s “keep”-variable. The second line calculates how much the proposer kept for himself and assigns the value to a variable “send”. Now you can use both new variables to inform the responder about the proposal made to him. Change “for all roles” to “only role 2” in the text box and type in the following instructions:

"Player 1 has decided to split $endow; as follows: $keep; for player 1 and $send; for you. You can accept the proposal or reject it. If you reject it, both get nothing."

Now you need an input element via which the responder can accept or reject the proposal. Insert an input element beneath the text box and insert a “new input field” within the input element. Change the type to “Buttons (Single Choice)”. Set the variable name to e. g. “accepted” and define the Input field as visible for “only role 2”. Write a text into the text box that should appear above the “accept” and “reject” button (e. g. “Your decision”). To insert these buttons type “2” into the text field next to “add new possible answer” and click on Plus.JPG. Insert “Accept” and “Reject” into the text fields. The values assigned to the decision buttons are very important. Choose the value “1” for the accept button and the value “0” for the reject button.

The second stage should start for a responder automatically as soon as “his” proposer has sent a proposal. Therefore delete the “start button” field in the lecturer field by clicking on Rubbish.JPG. Then insert an “automatic start” via “add new element”. Change the mode to “wait for others”. To display how many proposers and responders have already made their decisions on the lecturer’s screen, set the counter to “display” and the count to “by role”.
Stage 3: Results

When the responders have accepted or rejected the proposals you can display the results in a third stage. Add a new stage and name it e. g. “Results”. “Late arrival” again is “Not possible”. The two fields next to the “late arrival” field define how often and where to jump after finishing this stage. You can define the number of rounds you want to play. Choose “back to stage 1” and e. g. “2x” (for playing two rounds).

For both players the payoff depends on whether the responder accepted the proposal or not. You have to distinguish these two cases. To do so you use a program code (subjects) field again. You need one for “only role 1” and one for “only role 2”. The program for role 1 is:

$accepted=$findVariablePartner(“accepted);
$payoff=$keep*$accepted;
if($accepted==0) {
  $text=”Player 2 has rejected your proposal.”
} else {
  $text=”Player 2 has accepted your proposal.”
}

The program for role 2 is:

$payoff=$send*$accepted;
if($accepted==0) {
  $text=”You have rejected the proposal.”
} else {
  $text=”You have accepted the proposal.”
}

Then insert two text boxes in the participants field. Again one for role 1 and one for role 2. In these text boxes you inform the players about their final payoff. For role 1 the text could be:

You have proposed to split $endow; as follows: $keep; € for you and $send; € for player 2. $text; Your payoff is $payoff; €.

For role 2 the text could be:

Player 1 has proposed to split $endow; as follows: $keep; € for him and $send; € for you. $text; Your payoff is $payoff; €.

In the lecturer field you can show the results. Delete the start button that is implemented in a new stage by default. Then add a results bubble element. Select the variable “accept” for the x-axis with 0 as minimum and 2 as maximum value. Choose a label for the x-axis, e. g. “acceptance." Select the variable “keep” for the y-axis with 0 as minimum and $endow as maximum value. Choose a label for the y-axis, e. g. “proposal (amount kept)”. Select “display if stage is activated and after” and select “by role” in the field “count”.
Testing the game

To test the game, change into lecture mode. You can test the game on your own PC by clicking on Testpart.JPG in the top bar of the lecture mode. This opens a participant screen in a new tab. You will see the game just as your subjects will see it when actually playing the game. You can open as many screens as you want, where each screen represents a participant. After opening enough test participant screens click "Start" in the lecturer screen. Then you can go through the game with all test participants. 

Create a new game
=================

Assignment and Matching
=======================

----------
[[File:Matching.PNG]]

==Assignment at the beginning of a game==

Right before the first stage there is the button 'Assignment and Matching'. Here, you can specify whether you want to assign participants to treatments, groups, roles or a combination of all (complex assigment). classEx allows you to flexibly adapt to an unknown number of participants, meaning that you choose the number of different roles, the number of treatments and the size of groups. ClassEx then assigns participants automatically. Specifically, have following available options:

'''No assigment:''' Participants all are assigned to role 0, treatment 0 and group 0.

'''treatments:''' Allows you to assign participants to treatments. A division into treatments will distribute participants evenly over treatments. You can select any number of treatments between 1 and 10. Treatments will be distributed according to arrival in the experiment (e.g. with two treatments the first will be treatment 1, the second treatment 2, the third again treatment 1,...)

'''role and group:''' Allows you to assign participants to a number of different roles in the game. Participants will be allocated to role 1, role 2, role 3... alternately. Participants will also be assigned to a group. E.g. if you have defined 3 roles, a group will consists of role 1, role 2 and role3. If you want to have groups with asymmetric combination of roles please use complex assignment.

'''group''' Allows you to assign participants to groups (all participants will have the same role). Groups are filled one after each other. You are free to select any group size. 

'''treatment + role and group''' Allows you to assign both role+group and treatments. If combines the two above options.

'''complex assignment''' Allows you to assign participants to a different number of roles, treatments and groups.

<div class="quote">Tip: The so-called between-subject design examines how a controlled variation of the game influences the behaviour of different participants. This can be implemented using treatments. The groups in one treatment only interact with participants in their own treatment and never with participants of the other treatment. The game can be adapted for every treatment, for example by providing different information, altered probabilities of random events or diverse strategic interactions.</div>

==Matching==

If you have assigned participants, you can specify how you want them to be rematched if your game consists of several rounds. You can choose from the following options:

'''partner''' Participants stay in the same groups and keep their roles throughout the entire game.

'''random''' Participants are randomly assigned to a new role, group and treatment (if specified).

Absolute stranger matching, ensuring that participants never interact with players they have interacted with before, is not available. 

[[Random matching with constant roles]] is not provided as an option but can be implemented manually in classEx.

==Further settings==

On the page assignment and matching you can further choose if the role should be displayed in the header of the participants page and if the player id should be displayed there as well.

==Available roles==

Up to 13 roles are available (and an additional gray role 0 for no role assignment). Role 2 is distinguishable by a different figure to allow distinction for person who have red–green color blindness.

[[File:Allroles.png]]

This roles are standardized items and are shown in the header of the participant's page.

Define your stages
==================

[[Games]] consist of several stages. There are at least 2 stages, one for the decision input and one for the result output. Stages are ordered sequentially and are meant to be synchronization points in the game. Synchronization means that for the next stage to begin, all elements of the previous stage must have been finalized.

==Configuration of Stages==

Stages are points of synchronisation in a [[Games|game]]. Generally, the input phase is one stage and the results or output phase is a different stage, as the output can only be displayed after all [[Participants|participants]] have entered their input. Each stage consists of one or more [[Elements|elements]] (e.g. input, results, small programmes) that require the input of at least one participant. In the [[Editing Mode]], you can choose to give the stages names instead if numbers in order to identify them more easily. To give them a name, simply enter it in the box.

[[File:blub.JPG]]

===Rounds===
If you want to run one or more stages more than once, you can define rounds and determine how often you would like to return to a certain stage. If you determine the return value as 0 or if the stage has been run for the predetermined number of times, classEx will redirect you to the next stage right underneath. You can also determine which stage you want to return to if you play several rounds.

===Late arrival===
You can specify whether participants can arrive late, i.e. if they only just logged in. You can choose for this to be possible, not possible, or only possible in the first round.

===Move stages===
When you create a new stage, this stage will automatically be defined as the next stage. You can move stages by pressing [[File:ll.JPG]] or [[File:rr.JPG]]. The order in which stages are run is always from left to right.

===Add stage===
You can add a new stage by clicking on [[File:plus.JPG]] beside the tabs displaying the different stages or on the top right of the current stage. To change the order of stages see "move stages".

===Delete stage===
You can delete a stage by pressing [[File:rubbish.JPG]].

Add elements (display condition,…, mit Bsp…, general input)
===========================================================

General Information

Elements are the modules of each stage. A stage has two areas in which you can add modules: participants and lecturer.

You can chose from text elements, input elements (numerical input, likert scales, …), programme elements and output elements (histograms, bar charts, …). These can be combined and arranged as you like.


Tip: Input and output elements should be located in different stages in order to collect all input in the first stage. Then, the lecturer can synchronise the game and turn to the output elements in the next stage.


Element Number 	The elements are numbered (E1, E2, …). This also defines the order of display in a stage. Elements can be moved within a stage by pressing on the arrows Updown.JPG.
Element Type and Help 	Beside the number of the element, you can see the element type. Clicking on the info button next to the element type leads you to the respective description in this wiki.
Groups, Treatments and Roles 	If you have defined groups, treatments or roles, you can also choose whether the element shall be displayed for all groups, treatments or roles.
Delete Element 	You can delete the element by pressing Rubbish.JPG.
Copy Element 	You can copy an element by pressing Copyelement.JPG.
Cut and Paste 	You can cut and paste an element by pressing Cut.JPG.
Display Conditions 	You can specify the display conditions for an element by pressing Brille.JPG.


Elements for participants can be inserted by clicking on Addnewel.JPG. In the following, the elements are described in detail.
Elements for participants
Screenshot 	Name 	Brief description
Tbnewnew.JPG 	Text Box 	Element to display text (including variables)
Inputfield.PNG 	Input Element 	In this element you can insert several input fields.
Codenew.JPG 	Program Code 	Program snippets can be implemented to calculate results for each subjects.
Winner.PNG 	Winner's Notification 	If a game is played with real payoffs, this element displays the payoff code to participants. (only works together with winners' draw)
Matrixpay.JPG 	Payoff Matrix Game 	This is a special element for matrix games.
Contract participant.JPG 	Contract 	This element allows participants to make contracts
Camera.png 	Camera 	This element allows participants to make a photo of themselves.
Refer.JPG 	Element Reference 	A reference can be used to reuse elements and thereby avoid redundant elements.
	Javascript 	Program javascript snippets to implement more flexibly
Elements for lectureres

Elements for the lecturer are generally only displayed on the lecturer’s screen which is usually projected to a wall for all participants to see. The start button, text boxes, elements for payoff calculations and output displays are typical elements for the lecturer.
Screenshot 	Name 	Brief description
Tblec.JPG 	Text Box 	Element to display text (including varibales) on the lecturers' screen.
Startt.JPG 	Start Button 	A Start Button is needed to start a stage. You can also set an automatic start here.
Draw.JPG 	Winners' Draw 	If a game is played with real payoffs, this element draws the winners (only works togehter with winner's notification).
Codenew.JPG 	Global Program 	Progam snippets can be implemented to calculate results on the global level for all participants.
Randomdraw.PNG 	Lecturer Discrete Choice 	Lecturer Discrete Choice allows the lecturer to input data in the course of the game
Contracttable.JPG 	Contract table 	Contract tables give you an overview of contracts concluded by the participants.
Refer.JPG 	Element Reference 	An reference can be used to reuse elements and thereby avoid redudant elements.
Ress.JPG 	Result Element 	Different Result Elements like Pie Chars, Line Charts, Histograms... are available. 

Player
------

Lecturer
--------

Programs and PHP functions
==========================

Pre-Defined Variables
---------------------

Functions
---------

Testing (Diagnose mode)
=======================

You can access the diagnosis mode by clicking on the [[File:Steto.PNG]] symbol in the top bar of the [[Lecture Mode]].

Clicking on the symbol opens up a space beside the usual display on the lecturer's screen, which shows you all variables.

[[File:Stetot.PNG]]

The different tabs allow you to access the globals or the variables for each player. This makes it much programming and error finding much easier than having to jump back and forth between the lecture mode and the editing mode.


Test a Game

Before playing a game in your lecture, you can test the game on your own PC by clicking on Testpart.JPG in the top bar of the lecture mode. This opens a participant screen in a new tab. You will see the game just as your subjects will see it when actually playing the game. You can open as many screens as you want, which enables you to also test interaction between participants in games with several roles. 

Error spotting

If you try out the game you just programmed and find that something doesn't work, you can use the new Diagnosis mode for error spotting. This shows you all variables during the game in the lecture mode. 

Parameter
=========
parameter

By clicking on this button, you can set different parameters of a game that can be changed easily in the lecture mode if you want to play the same game several times with different parameters.

Here is an example for a public goods game:

Param.JPG


Languages 
=========
Languages

For some elements, you can enter the text in two different languages, English and German.

Gereng.PNG


To switch the languages on and off, you can click on the flag Flags.PNG symbols above the elements.

For other elements, this function has not been implemented yet. In this case, you need to enter both languages in one text box, separated by $$, for more information see Text Box. 

Tool Comparison 
===============
Tool Comparison 

Here you find an overview how classEx compares to other tools. It was last updated in September 2015 and is based on available information on the respective websites (see references below).

==Participation==
{| class="wikitable" style="border:solid 2px #999999;font-size:96%;"
|- class="hintergrundfarbe8"

! style="width:15%;font-size:103%;" | 
! style="width:15%;font-size:103%;" | classEx
<span style="font-size: x-small;">Giamattei & Lamsbdorff 2015</span>
! style="width:15%;font-size:103%;" | Econ Port 
<span style="font-size: x-small;">Cox and Swarthout 2006</span>
! style="width:15%;font-size:103%;" | VeconLab
<span style="font-size: x-small;">Holt 2015</span>
! style="width:15%;font-size:103%;" | MobLab
<span style="font-size: x-small;">MobLab 2015</span>
! style="width:15%;font-size:103%;" | oTree
<span style="font-size: x-small;">Chen et al. 2015</span>
! style="width:15%;font-size:103%;" | z-Tree
<span style="font-size: x-small;">Fischbacher 2007</span>
|- 
! Device for participation
! Platform-independent
! Computer
! Computer
! Platform-independent
! Platform-independent
! Computer
<span style="font-size: x-small;">Windows only</span>
|-
! Optimized for mobile use
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;">Plugin not compatible</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;">Not Optimized</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
|-
! Free Use
! [[file:Yes2.png | 20px]]
! [[file:Yes2.png | 20px]]
! [[file:Yes2.png | 20px]]
! [[file:No.png | 20px]]
<span style="font-size: x-small;">Research: $500 + session fee 
Teaching:$18 per student/class
</span>
! [[file:Yes2.png | 20px]]
! [[file:Yes2.png | 20px]]
|-
! Easy Access
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;">no download and registration</span>
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;">no download, but registration</span>
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;">no download, but registration</span>
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;">download optional, but registration</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;">no download and registration</span>
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;">download and registration</span>
|}

==Games==
{| class="wikitable" style="border:solid 2px #999999;font-size:96%;"
|- class="hintergrundfarbe8"
  
! style="width:15%;font-size:103%;" | 
! style="width:15%;font-size:103%;" | classEx
<span style="font-size: x-small;">Giamattei & Lamsbdorff 2015</span>
! style="width:15%;font-size:103%;" | Econ Port 
<span style="font-size: x-small;">Cox and Swarthout 2006</span>
! style="width:15%;font-size:103%;" | VeconLab
<span style="font-size: x-small;">Holt 2015</span>
! style="width:15%;font-size:103%;" | MobLab
<span style="font-size: x-small;">MobLab 2015</span>
! style="width:15%;font-size:103%;" | oTree
<span style="font-size: x-small;">Chen et al. 2015</span>
! style="width:15%;font-size:103%;" | z-Tree
<span style="font-size: x-small;">Fischbacher 2007</span>
|-
! Asynchronous Games
! [[file:No.png | 20px]]
<span style="font-size: x-small;">To be implemented
</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
|-
! Between-subject design within a session
! [[file:Yes2.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:Yes2.png | 20px]]
! [[file:Yes2.png | 20px]]

|}

==Results==
{| class="wikitable" style="border:solid 2px #999999;font-size:96%;"
|- class="hintergrundfarbe8"

! style="width:15%;font-size:103%;" | 
! style="width:15%;font-size:103%;" | classEx
<span style="font-size: x-small;">Giamattei & Lamsbdorff 2015</span>
! style="width:15%;font-size:103%;" | Econ Port 
<span style="font-size: x-small;">Cox and Swarthout 2006</span>
! style="width:15%;font-size:103%;" | VeconLab
<span style="font-size: x-small;">Holt 2015</span>
! style="width:15%;font-size:103%;" | MobLab
<span style="font-size: x-small;">MobLab 2015</span>
! style="width:15%;font-size:103%;" | oTree
<span style="font-size: x-small;">Chen et al. 2015</span>
! style="width:15%;font-size:103%;" | z-Tree
<span style="font-size: x-small;">Fischbacher 2007</span>
|-
! Immediate graphical results at the end of the experiment
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;">Limited
</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:Yes2.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
! [[file:No.png | 20px]]
<span style="font-size: x-small;"> &nbsp;</span>
|-
! Data Output
! XLS
! XML
! Unformated
! PDF
! CSV
! XLS

|}

==Own Experiments==

{| class="wikitable" style="border:solid 2px #999999;font-size:96%;"
|- class="hintergrundfarbe8"
  
! style="width:15%;font-size:103%;" | 
! style="width:15%;font-size:103%;" | classEx
<span style="font-size: x-small;">Giamattei & Lamsbdorff 2015</span>
! style="width:15%;font-size:103%;" | Econ Port 
<span style="font-size: x-small;">Cox and Swarthout 2006</span>
! style="width:15%;font-size:103%;" | VeconLab
<span style="font-size: x-small;">Holt 2015</span>
! style="width:15%;font-size:103%;" | MobLab
<span style="font-size: x-small;">MobLab 2015</span>
! style="width:15%;font-size:103%;" | oTree
<span style="font-size: x-small;">Chen et al. 2015</span>
! style="width:15%;font-size:103%;" | z-Tree
<span style="font-size: x-small;">Fischbacher 2007</span>
|-
! Development of own games
! [[file:Yes2.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:Yes2.png | 20px]]
! [[file:Yes2.png | 20px]]
|-
! Backend system
<span style="font-size: x-small;">A backend system means that like in z-Tree experiments can be set by building together predefined elements so that only little programming is required.</span>
! [[file:Yes2.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:No.png | 20px]]
! [[file:Yes2.png | 20px]]
|- 
! Programming Language
! PHP, AJAX
! JAVA
! PHP
! No info
! Phyton, Django
! C++
|}

==References==

Chen, D. L., Schonger, M., & Wickens, C. (2015). oTree-An Open-Source Platform for Laboratory, Online, and Field Experiments. https://mpra.ub.uni-muenchen.de/62730/1/MPRA_paper_62730.pdf. Accessed 23 August 2015.

Cox, J. C., & Swarthout, J. T. (2011). EconPort: Creating and Maintaining a Knowledge Common. In C. Hess & E. Ostrom (Eds.), Understanding knowledge as a commons: From theory to practice (pp. 333–348). Cambridge, Mass.: MIT Press.

Fischbacher, U. (2007). z-Tree: Zurich toolbox for ready-made economic experiments. Experimental Economics, 10(2), 171–178.

Giamattei, M.,& Lambsdorff, J. G. (2015). classex - an online software for classroom experiments. Working Paper. https://www.researchgate.net/publication/280153877_classEx_-_an_online_software_for_classroom_experiments

Holt, C. (2015). University of Virgina Veconlab. http://veconlab.econ.virginia.edu. . Accessed 23 August 2015.

Moblab. (2015). Moblab: A playground for decisions. https://www.moblab.com/. Accessed 23 August 2015.
