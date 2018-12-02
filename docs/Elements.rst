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
The text box is equipped with a WYSIWG editor which allows you to insert tables, symbols etc. If you double-click into the text element, The WYSIWG editor opens. You can switch back to the normal text box by clicking on the **<>** symbol. 

If you are not in the WYSIWG editor, you can use standard HTML to design your texts. You can do e.g. the following:

.. code:: html

This is a text box with a <b>bold text</b> and a <span style="font-size: x-small;">small</span> text. You can also show pictures <img src="https://yourownserver.de/adress_of_picture.png" stlye="with: 20px"> or add tables <table><tr><td>Tab 1</td><td>10</td></tr></table>.

Special Characters
-------------------

=========== ============== ===============
Special     Name 		   Function Example
=========== ============== ===============
role1.png   Symbol Role 1  Red participant symbol |pic_role1| is displayed. 
role2.png   Symbol Role 2  Green participant symbol |pic_role2| is displayed.
$variable;  Variables      Beside normal text, you can also insert variables into the text box. If you have defined variables (see :ref:`Programming`), you can have these displayed by inserting the character "$", the variable name followed by ";". Make sure not to forget the ";" at the end! Variables and normal text can be combined
=========== ============== ===============

Make sure that role1.png, role2.png,... are followed by a space. Otherwise the figure will not be replaced.

.. |pic_role1| image:: _static/pic/role1.PNG
	:width: 15px
.. |pic_role2| image:: _static/pic/role2.PNG
	:width: 15px


Conditional text
-----------------

So far we have only tackled how to read the PHP variables and display them in he text field (e.g. $variable;), but sometimes we would like to display conditional text. For example we might have a bool variable that tells whether a participant is buyer or seller. We can achieve this task by a program element where you define:

.. code:: php

if ($isBuyer) $buyerText="You are buyer"; else $buyerText="You are seller";

Then you can output $buyerText; in the text box.

Element Reference
~~~~~~~~~~~~~~~~~

.. image:: _static/Refer.JPG
    :alt:  300p

In order to avoid redundancies, you can reference elements and add them in a different place in the game (instead of copying them directly) For this, you can use the reference element. If the original element is altered, the reference is adapted automatically. The reference is created by entering the stage number and the element number you are referring to. 

.. note:: If you require the same text in two stages, for example, an element reference is a far more elegant version than a simple copy because any changes to the original element are adopted automatically.

.. note:: Please notice that the display condition is not taken from the referenced element but  from the reference itself.

.. warning:: If you change the order of referenced elements, the reference does not automatically adapt, but has to be changed manually.

Program code
~~~~~~~~~~~~

Program snippets can be implemented to calculate results for each subjects. For further information see :ref:`Programming`.

Elements for participants
==========================

Input element
~~~~~~~~~~~~~

In this element, you can insert several input fields. These are numbered #1, #2, …. You can add input fields by clicking on *add new input field*. The input fields are displayed one after each other.

The following settings are available for every input field. You can determine the type of input field and define a variable name. The variable name can then be used in programs. For example, if your variable is called $e, you can access it by writing "$e;" in a text box or use $e in a program element. Furthermore, you can delete an input field by clicking on |pic_delete|. You cannot delete the first input field (#1).

.. |pic_delete| image:: _static/pic/reject.PNG
				:width: 15px

.. warning:: Please notice that only one input element is allowed per stage. For several inputs add additional input fields to the first input element.

Input elements always provide a submit button automatically. In the following, the different types of input fields are described in more detail.

Numeric input field
--------------------

.. image:: _static/NumericInput1.JPG
    :alt:  300px

The name of the input field is used as the label and is displayed on the left hand side of the input field when it is displayed to participants. You can specify the minimum and the maximum and the number of decimal places allowed. If entries are different from these specifications, participants will see an error notification and will be requested to correct their entry.

In addition, a unit (e.g. %, €, mm, …) can be specified that will be displayed on the right of the input field (here "years"). You can also set a default value that is displayed to participants at the start. Further, you can determine whether input is compulsory. In this case, participants cannot proceed without entering a value. *Output only* can be used, if an input field shall only display output. 

.. image:: _static/NumericInput2.JPG
    :alt:  300px


.. note:: The numeric input automatically corrects minor inconsistencies of participants. classEx checks whether participants adhere to the minimum and maximum values, rounds numbers according to the predetermined decimal places and automatically adapts the decimal separator by adding zeroes. classEx also automatically changes the input to numeric on mobile devices and shows the correct keyboard.

Text input
----------

.. image:: _static/TextInput.JPG
    :alt:  300px

Text input fields enable you to let participants enter a text. You can specify the minimum and maximum amount of characters and a default text. The number of rows determines the size of the text input field.

Buttons, simple list and drop list (single choice)
----------------------------------------------------

.. image:: _static/develop/buttons.PNG
   :height: 500px

This type of input is used for discrete decisions. Besides the text that is shown above the buttons, you can specify the different answer options. Participants make a decision by choosing one of the options. The order of options can be altered by clicking on the arrow. You can also delete or add options. You can also select if the options should be displayed as stated or randomly (different for each participant). You can set the input as required. You can mark the correct answer by clicking on the symbol |pic_correct|. In this case, if you use the single/multiple choice result element for the lecturer, the correct answer is marked there.

.. |pic_correct| image:: _static/pic/correct.PNG 
	:width: 15px

You can implement single choice questions using buttons, simple lists or drop lists. This is what they look like in the participants' display. The settings are the same for these options.

.. image:: _static/ButtonsAndSelection2.JPG
    :alt:  300px
    
.. image:: _static/ButtonsAndSelection3.JPG
    :alt:  300px
    
.. image:: _static/ButtonsAndSelection4.JPG
    :alt:  300px

Checkboxes (multiple choice)
------------------------------

Choosing multiple options is possible by using checkboxes. Checkboxes work in exactly the same way as single choice options. Only the form of display is slightly different, as these are displayed as a list from which participants can pick several options. This way, multiple inputs can occur in one stage. Additionally to the single choice, you can specify the minimum and maximum number of choices and the number of answers per row.

Radioline
---------

ADD PICTURES 

Radiolines, like Likert scales, offer stepwise input. For this, you need to specify the minimum and maximum. Furthermore, you need to enter a description for the left and right hand side.


Slider
------

Sliders are a similar concept. In this form of input, the participant moves a slider along a bar of predetermined positions. For sliders you have to determine the number of steps. 

Defaults can be set for radiolines and sliders. If no default is set, the radioline is empty and the slider is positioned in the middle of the bar.

Hidden field
-------------

Next button
------------



Other input fields
------------------

There are other input fields available (urn, infotext, mean of all input fields). This are outdated and should only be used with care.

The contract input field is also oudated. Please use the `Contract`_ element instead.

Additional settings
-------------------

button label

confirmation message

hide decision after sending

directly to next stage

show button later





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

Settings
--------

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

Output
------

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

Javascript program
~~~~~~~~~~~~~~~~~~~

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

Filled in form (outdated)
~~~~~~~~~~~~~~~~~~~~~~~~~~

This element allows you to display the filled in input element of the previous stage.


Elements for lecturers
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

