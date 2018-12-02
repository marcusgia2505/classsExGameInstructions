.. _Elements:

=========
Elements
=========

Elements for lecturers and participants
=======================================


Text box
~~~~~~~~~



.. image:: _static/Textbox.JPG
    :alt:  300px

The text box is the simplest element. The entered text will be displayed to the participants.
The text box is equipped with a text editor which allows you to insert tables, symbols etc. If you double-click into the text element, you see the text as it will be displayed to participants.

- Special Characters

=========== ============== ===============
Special     Characters     Function Example
=========== ============== ===============
$$          Multilanguage  Support If you want to provide German and English support, you can write both texts in the same textbox and seperate them by "$$". E.g. "Das ist Deutsch$$This is English" displays the German text if the selected language is German and English if it is English.
role1.png   Symbol Role 1  Red participant symbol |role1| is displayed.
role2.png   Symbol Role 2  Green participant symbol |role2| is displayed.
$variable;  Variables      Beside normal text, you can also insert variables into the text box. If you have defined variables (see element [[Program Code|Program]]), you can have these displayed by inserting the character "$", the variable name followed by ";". Make sure not to forget the ";" at the end! Variables and normal text can be combined
=========== ============== ===============

.. |role1| image:: Role1.JPG
.. |role2| image:: Role1.JPG

- Configuration for Participants

For participants you can chose to display the text box only for certain roles, treatments or groups (if defined). You can simply choose who the box shall be displayed for in the drop down menu above the text.

Further, you can determine where the text shall be aligned (left, center or right).

- Conditional text

So far we have only tackled how to read the php variables and display them in he text field (e.g. $variable;), but sometimes we would like to display conditional text. For example we might have a bool variable that tells whether a participant is buyer or seller. We can achieve this task by the use of javascript code embedded in our text element:

| Endowment: $endowment;. <span id="isbuyer"></span>
| <script>$("#isbuyer").text("$isBuyer;" === "1" ? "You are Buyer" : "You are Seller")</script>

since ClassEx supports JQuery, it is very easy. We create a span (an html tag to which we can easily add text) and than using the javascript syntax we add text to this tag with the id "isbuyer". We could also have used another id. Its only important that this id is unique in resulting html document. The Jquery text function gets the text we want to add as an argument. In this example we used the ternary Operator since it produces shorter code, but we could also have used a if else statement or more elaborate conditions. 

Element Reference
~~~~~~~~~~~~~~~~~

.. image:: _static/Refer.JPG
    :alt:  300p

In order to avoid redundancies, you can copy elements and add them in a different place in the game. For this, you need a reference, i.e. the element that shall be copied. If the original element is altered, the copy is adapted automatically. The reference is created by entering the stage number and the element number you are referring to. If you require the same text in to stages, for example, an element reference is a far more elegant version than a simple copy because any changes to the original element are adopted automatically.

Please notice that the display condition is not references but taken from the element which calls the reference.

Program code
~~~~~~~~~~~~

Program snippets can be implemented to calculate results for each subjects. For further information see Program code.

Elements for participants
==========================

Input element
~~~~~~~~~~~~~

In this element you can insert several input fields. These are numbered #1, #2, …. You can add input fields by clicking on “add new input field". The input fields are displayed one after each other.

The following settings are available for every input field. You can determine the type of input field and define a name. The name can then be used in programmes and will give out the value of the variable. For example, if your variable is called “e", you can access it by writing “$e;". For more details see program. Furthermore, you can delete an input field by clicking on http://classex.uni-passau.de/classex3/pic/reject.png. You cannot delete the first input field (#1).

	**Please notice that only one input element is allowed per stage. For several inputs add additional input fields to the first input element.**

In the following, the different sorts of input fields are described in more detail.

Numeric Input Fields
--------------------

Numbers can be inserted into this input field. 

.. image:: _static/NumericInput1.JPG
    :alt:  300px

The name of the input field is used as the label and is displayed on the left hand side of the input field when it is displayed to participants. In the [[editing Mode]], you can specify the minimum and the maximum and the number of decimal places allowed. If entries are different from these specifications, participants will see an error notification and will be requested to correct their entry.

.. image:: _static/NumericInput2.JPG
    :alt:  300px

In addition, a unit (e.g. %, €, mm, …) can be specified that will be displayed on the right of the input field (here "years"). You can also set a default value that is displayed to participants at the start. Further, you can determine whether input is compulsory which is not the case for voluntary information for example.

"Output only" can be used, if an input field shall only display output. This can be necessary for calculations. For example, if participants are required to allocate different parts of income to different purposes, an "Output only" field can be used to display how much income is still left after filling in the input fields.

	Hint: The numeric input automatically corrects minor inconsistencies of participants. classEx checks whether participants adhere to the minimum and maximum values, rounds numbers according to the predetermined decimal places and automatically adapts the decimal separator by adding zeroes. classEx also automatically changes the input to numeric on mobile devices and shows the correct keyboard.

Text Input
----------

.. image:: _static/TextInput.JPG
    :alt:  300px

Text input fields enable you to let participants enter a text. You can specify the minimum and maximum amount of characters if required.

- Editing Buttons and Selection Lists (single choice)

.. image:: _static/ButtonsAndSelection1.JPG
    :alt:  300px

This type of input is used for discrete decisions. Besides the text that is shown above the buttons, you can specify the different answer options. Participants make a decision by choosing one of the options. The order of options can be altered by clickingon the arrow [[File:up.JPG]]. The correct answer can be specified and you can also delete or add options. You can also select if the options should be displayed in order or randomly (different for each participant).

You can implement single choice questions using buttons, simple lists or drop lists. This is what they look like in the participants' display.

.. image:: _static/ButtonsAndSelection2.JPG
    :alt:  300px
    
.. image:: _static/ButtonsAndSelection3.JPG
    :alt:  300px
    
.. image:: _static/ButtonsAndSelection4.JPG
    :alt:  300px

Choosing one of the options when using buttons submits the data, therefore, this type of input can only be used once in a stage. Multiple input fields (e.g. a single choice question and a numeric input field) should not be inserted as this leads to input errors. For simple lists and drop lists the choice needs to be submitted by pressing the submit button.

Choosing multiple options is possible by using [[Check Boxes]]. Checkboxes work in exactly the same way as single choice options. Only the form of display is slightly different, as these are displayed as a list from which participants can pick several options. This way, multiple inputs can occur in one stage.

Radiolines and Sliders
----------------------

Radiolines, like Likert scales, offer stepwise input. For this, you need to specify the minimum and maximum as well as the number of steps (e.g. Min1, Max 7 and Steps 6 would lead to integers and Steps 12 would lead to steps of the size 0.5). Furthermore, you need to enter a description for the left and right hand side.

Sliders are a similar concept. In this form of input, the participant moves a slider along a bar of predetermined positions.

Defaults can be set for radiolines and sliders. If no default is set, the radioline is empty and the slider is positioned in the middle of the bar.

Checkboxes
----------

Check boxes allow for choosing multiple answers. Options can be set just as described for selection lists ([[Buttons and Selection Lists (single choice)|single choice]]). Further, the minimum and maximum number of answers must be specified. It is possible to set a default. You can also select if the options should be displayed in order or randomly (different for each participant).

Other Input Fields
------------------

Average over all input fields
	This option saves the average over all input fields which is not displayed to the user. The average is created automatically by calculating the mean over several numeric inpu fields (e.g. radiolines, numeric input fields, sliders).

Filled in input
~~~~~~~~~~~~~~~

This element allows you to display the filled in input field of the last stage.

Winner's Notification
~~~~~~~~~~~~~~~~~~~~~

If a game is played with real payoffs, this element displays the payoff code to participants. (only works together with winners' draw) 

.. image:: _static/Winner.PNG
    :alt:  300p

A winning notification is necessary for games with monetary payoff. The participants who are randomly drawn receive a winning notification as well as a code to cash in their earnings. You can adapt the message that is displayed in the winning notification. The amount of earnings can be determined in the field “Payoff(variable) in €". Besides a fix amount, you can also enter a variable that is calculated beforehand. If, for example, the variable “$payoff;" is calculated in a programme during the game, you can enter this variable in the earnings field.

	Hint: The winning notification can only be displayed if you also define a [[Winners'_Draw|winner's draw]] on the lecturer side. Otherwise no winner can be determined.

Clicking on the little info circles above the boxes will show you what will be displayed if you leave the boxes blank.

	Important: Payoffs per game are restricted to 100€ per default. If you need higher payoffs, you have to overwrite the variable $maxWin in a global program (e.g. $maxWin=1000;).

Payoff Matrix Game
~~~~~~~~~~~~~~~~~~

.. image:: _static/Matrixpay.JPG
    :alt:  300p

This element helps display the payoff for a two role game easily with a matrix. Alternatively, you can also do this through a program. In this element, you need to specify which input field contains the decision of the respective participant for the row participant and for the column participant. The labels of the matrix are determined by the specified input fields. In the table, you enter the payoff for the row participant first followed by the payoff for the column participant. The payoff is stored as variable $payoff; which can then be used for the winning notification or further calculations.

Contract
~~~~~~~~

.. image:: _static/Contractparticipant.JPG
    :alt:  300p

With this element, you can enable participants to form contracts. By adjusting the settings, you can customise the contract to your needs.

**Please note that you need to set seperate contract elements for buyers and sellers.**

- Functionality

.. image:: _static/Seller.PNG
    :alt:  300p

.. image:: _static/Buyer.PNG
    :alt:  300p

Contracts can be used to trade a commodity between subjects in real time. Subjects move around in the classroom and talk to each other. When they agreed on a price they enter it into the input mask together with the signature of the counterparty (see seller screen). The counterparty has to accept the trade (or reject it, see buyer screen).

- Settings

sell offers/buy offers
	If you turn this on, you allow for sell or buy offers made by the respective subject.

set quantities
	allows to set quantities (otherwise quantity is always 1). Prices are set as price/unit.

no signature
	allows to disable the signature. The signature is needed for sell and buy offers to be send to a specific person. E.g. if the buyer can make buy offers, she needs the signature of the seller to send the offer to.

max # contracts
	maximum number of (accepted) contracts

currency/min price/max price/decimal place
	Currency of the prices and minimum, maximum and decimal places.

maximum quantity
	maximum quanity a subject is allowed to possess

products
	at the moment only one typoe of product can be traded. You can specify a name (or a small image) and the initial amount of the good (e.g. the seller has 1 unit, the buyer 0 units).

- Output

The contracts made can be shown at the lecturer's screen with the contract table. In addition, there are special functions in globals and subjects programs to retrieve contracts. All contracts are also stored in the standard excel file which can be retrieved in the data menu. 

Camera
~~~~~~

.. image:: _static/Camera1.PNG
    :alt:  300p

With this element, you can enable participants take a picture of themselves.

- Settings

The filename, under which the picture is stored, has to be defined. Additionally, you can define if participants are allowed to retake a picture. Then only the last picture taken is saved.

.. image:: _static/Camera2.PNG
    :alt:  300p

- Informed Consent

Participants are asked by the browser if the browser can access the webcam or not. Please make participants aware that they do not have to take a picture and ask them for their consent.

- Retrieving Pictures

Pictures can be retrieved in the following ways:

At another participant' screen
	You can use the normal variable notation ($image;) to display pictures in textboxes.

At the lecturer screen
	You can use $getValues(...) to retrieve the pictures of all participants and display them.

From the stored data
	In the downloaded data you find stored images in the subjects table. They can are base64 decoded and can be encoded with free online tools. Just take away "data:image/jpeg;base64," from the string, so that it starts e.g. with "/9j/....".

Javascript
~~~~~~~~~~

- Reading php variables

To read php variables one currently neads a two step approach:
	* write php variable in the text field
	* parse textfield content in javascript using jquery
	* [optional] hide textfield

Assume we have a php variable <code>$foo</code> that containing an array we want to use as an javascript array.

- Textfield content:

	| <pre><div id="php_var_foo" hidden>$foo;</div></pre>
	| The id does not need to have this format, but it must be unique and match the variable used in the Javascript field

- Javascript-field content:

	| var foo = JSON.parse($('#php_var_foo').html());
	| $('#php_var_foo').parent().hide(); // optional

This finds the html element with the id of the div containing the variable content. It's inner html (the content) is taken and than parsed. Now the variable foo in javascript contains the content of the php variable foo.

[Optional] Hide the parent of the div containing the variable.

- Writing php variables

This can be achieved via hidden input fields that are triggered via JQuery calls


Elements for Lecturers
======================

Start Button and Automatic Start
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The start button is used to initiate a stage. Each stage '''requires a start button''' apart from stages that has a result element. Result elements have their own buttons. 

There are two options. A start button which has to be clicked by the experimenter or a automatic start.

Start Button
------------

.. image:: _static/Startbutton.PNG
    :alt:  300p

The start button can be configured according to the needs. 

* Name: You can name the button (e.g. Start Trade).
* Feature: Instead of starting the current stage, you can also use the start button to jump to different stages. 
* Confirmation message: you can set if a pop-up should appear after clicking to confirm the action. 
* Count: You can set the counter which appears after the start button is clicked. It can count decisions (also by role, treatment or group if set). 

Automatic Start
---------------

.. image:: _static/Automaticstart.PNG
    :alt:  300p

The automatic start button allows you to start stages when subjects finished the previous stage.

The mode can be set to:

start if possible
	if a subjects finishes the previous stage, it is forwarded to the next stage.

wait for all
	subjects are only forwared if everyone in the group is done with the previous stage.

no forwarding
	subjects are not forwarded (This feature is only used if subjects forward themself by clicking on a button. This can be set in additional settings of the input element).

Count
	You can set the counter which appears after the start button of the previous stage is clicked. It can count decisions (also by role, treatment or group if set).
Counter
	Setting this additionally allows you to deactivate the counter completly.



Winner's Draw
~~~~~~~~~~~~~

.. image:: _static/Draw.JPG
    :alt:  300p

This element should be implemented in the last stage and draws a winner from among all participants. The earnings should be calculated individually on the participant side (see [[Winner's_Notification|winning notification]] for participants). You can determine whether single participants or coupled participants shall be drawn. Drawing coupled participants only makes sense if you have defined roles. You can also decide how many winners you want to draw.

 Important: Payoffs per game are restricted to 100€ per default. If you need higher payoffs, you have to overwrite the variable $maxWin in a global program (e.g. $maxWin=1000;).

	Hint: For games with two roles it is advisable to draw coupled participants as winners because the possibility that only one of the two participants could be drawn might overshadow considerations of fairness or reciprocity. Experience has shown that earnings of less than 5€ are usually not cashed in. Therefore, games should be calibrated in a way that ensures that earnings are at least 10€.

**Important: Winners are only drawn from participants who made a decision to avoid inactive participants to be drawn. Therefore it does not make any sense to put the winners' draw in the first stage.**

You should draw winners only once in a game as the payoffs codes do not distinguish between rounds.

Lecturer Discrete Choice
~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: _static/Randomdraw.PNG
    :alt:  300p

- Usage

With this element the lecturer/experimenter can make decisions for all participants during the game, e.g. tossing a coin in front of the class and entering the value in classEx so that payoffs can be calculated based on the coin toss.

- Settings

name
	This name will be displayed on the screen to identify the input button.

variable name
	The value will be saved under this name as a global variable and can be retrieved by that name.

for each participant
	If you switch this on, you can set the value for each participant separatly. The value will be stored as a global variable in an array with the participant ID as index.

default
	You can set a default.

options
	You can specify options with different values.

update
	If you switch on the update, the element will check every two second if new participants arrived (only necessary when you switched on "for each participant").

Contract table
~~~~~~~~~~~~~~~~~


.. image:: _static/Contracttable.JPG
    :alt:  300p

With this element, all contracts that were entered into by participants as well as a chart and the average are displayed on the lecturer's screen.


.. image:: _static/Ctable4.PNG
    :alt:  300p

.. image:: _static/Ctable2.PNG
    :alt:  300p

.. image:: _static/Ctable3.PNG
    :alt:  300p

.. image:: _static/Ctable1.PNG
    :alt:  300p

- Functionality

In the contract table you have several tabs where you can jump between. You can see them in the pictures on the right hand side.

Contracts
	lists all contracts made.

Averages
	yields overview statistics for each round (mean, median, min, max, std dev)

Chart
	show contracts made over time. In case of different quantities it also shows a bubble chart for the combination of quantities and prices.

Predicition
	shows a predicition (if set). To create a prediction the variables $demand and $supply have to be filled in a global program. $supply and $demand should be arrays which contain prices as index and the resulting quantity as a value.

- Settings

value array
	gives the name of a (pre-filled) array which contains the role of the participant as index and the respective buyer or seller value as value. This is shown in the table as buyer/seller value.

label
	all labels in the table can be changed according to needs (seller/buyer/seller value/buyer value/price).

profit variables
	can be left empty.

show quantities
	additionally shows quantities in the contract table and a bubble chart with quantities and prices.

Result Element
~~~~~~~~~~~~~~~

For displaying the results of a game various types of charts are available. Note that you can only display saved subject variables.

Whenever you can select variables in a field you only need to insert the variable name (e.g. "payoff"). Ordinary input fields require the usual php notation (e.g. "$payoff;").

The program code does not distingiush between binary 0 and numeric 0. Some result elements, however, cannot display binary 0. Make sure to convert binary 0 in numeric 0 in the program code (e.g. "if($accept == 0) {$accept = 0;}") in case you want to display it in a result element.

Under the header “count", you can determine whether results shall be displayed separately for groups, treatments or roles (if defined). Further, you can determine for some result elements whether you want the button “show results" to be displayed or not. Not displaying the button can be useful, if you want to display several diagrams underneath each other. You do, however, need at least one button per stage. You can use a normal start button element as well.

Results Single / Multiple Choice Questions
------------------------------------------

.. image:: _static/Smc.JPG
    :alt:  300p

The results are displayed with percentage bars.

.. image:: _static/Singlechoice.PNG
    :alt:  300p

The following options can be changed:

Count
	Participants are counted all together (or per treatment / role).
Show element
	Always display element or only if stage is activated.
Input
	The variable which should be displayed (here: stage #1 input field #1). 

The element automatically detects if the input is multiple choice or single choice. Hovering over the bars gives the absolute frequency of participants who opted for that option. The element should only be used with input fields with predefined options (otherwise you should use the counter result element).

Results Histogram
------------------

.. image:: _static/Numericindic.PNG
    :alt:  300p

.. image:: _static/Hist.PNG
    :alt:  300p

The following options can be changed:

Variable
	Choose which variable you want to display

Show element
	Element is always displayed or only if stage is activated.

Min
	Minimum of the histogram (Default 0)

Max
	Maximum of the histogram 

Bin
	How the values shall be pooled into “bins". For example, if you define the bin width: 10, the data will be pooled in brackets of ten.

X-Line
	Vertical Line is drawn at this x-value (e.g. to specify a correct or true value)

Count
	Participants are counted all together or per treatment / role. This can be changed in drop down menu at the bottom.


	Hint: All values that are larger than the displayed maximum value are automatically pooled into the last bin.</div>

Results Line Chart
-------------------

.. image:: _static/Result_linechart.PNG
    :alt:  300p

.. image:: _static/Commons.PNG
    :alt:  300p


A line chart enables the display of the results of several rounds. The following options can be changed:

Count
Participants are counted all together (or per treatment / role).

Button
	A button to start the result stage is displayed (or not).
Input
	The variable which should be displayed (here: stage #496 input field #1 (variable name "beitrag")). 
Max x-Axis
	Maximum of x-Axis
Max y-Axis
	Maximum of y-Axis
Label x-Axis
	Label of x-Axis
Label y-Axis
	Label of y-Axis

If no maximum is determined, the programme will automatically use the maximum of the input field. You can label both axes.

The line chart automatically calculates the average of the input variable over all subjects, per group or per treatment.
If the input variable is a binary variable the result is diaplayed in percent.

Results Bubble
---------------

.. image:: _static/Bubble.JPG
    :alt:  300p

.. image:: _static/Bubble2.JPG
    :alt:  300p

Displays a bubble chart, which can be useful for trust games, for example.

You can define the variables to be displayed on the x-axis and the y-axis as well as a minimum and a label for each axis.
 
Results Counter
----------------

.. image:: _static/Counter.JPG
    :alt:  300p

.. image:: _static/Bc.PNG
    :alt:  300p

The counter enables you to display the relative frequency with which a specific answer was chosen. If participants are required to choose a pair of answers, like in the faces beauty contest for example, you can also display how often a specific pair of answers was chosen.

Hovering over the bars gives the absolute frequency of participants who opted for that option. 

Using a multiple choice input field will result in the listing of combined answers. E.g. You can select A, B, C (multiple choice). Then the counter elemnet will display who many percent chose A, A&B, A&C,... If you want to have the items analysed seperately (only A, B, C) you should use the Results Single / Multiple Choice Questions (see above). 

Results Game Matrix
--------------------

.. image:: _static/Qqq.JPG
    :alt:  300p

.. image:: _static/Qq.JPG
    :alt:  300p

If a game is played with two different roles, the results can be displayed as a matrix. The settings are the same as for the participant screen. If you have defined treatments, you can decide whether the results shall be displayed per treatment or altogether.

If you have several rounds, the matrix calculates the results overall rounds. If you want to show temporal structures (e.g. learning), please use the time line diagram.

	Hint: The displayed matrix only determines the image on the lecturer’s screen and not the payoff for participants. The payoff is calculated individually for the participants (either through the element "payoff for 2 roles" or through a program).

Other result elements
----------------------

Other result elements include likert scales and pie charts.

