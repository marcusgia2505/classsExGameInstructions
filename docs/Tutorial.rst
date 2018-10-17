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

.. code-block:: php

	$keep = $findVariablePartner("keep";$round);
	$send=$endow-$keep;

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