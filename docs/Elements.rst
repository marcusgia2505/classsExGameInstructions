.. _Elements:

=========
Elements
=========

Elements for lecturers and participants
=======================================


Text box
~~~~~~~~~


.. image:: _static/elements/text_field.png
    :width: 49%
.. image:: _static/elements/text_field2.png
    :width: 49%

The text box is the simplest element. The entered text will be displayed to the participants or a the lecturer screen depending where you place the element. The text box is equipped with a WYSIWG editor which allows you to insert tables, symbols etc. If you double-click into the text element, the WYSIWG editor opens (see left figure). You can switch back to the normal text box by clicking on the **<>** symbol (see right figure). 

If you are not in the WYSIWG editor, you can use standard HTML to design your texts. You can do e.g. the following:

.. code:: html

	This is a text box with a <b>bold text</b> and a <span style="font-size: x-small;">small</span> text.
	
	You can also show pictures <img src="https://classex.uni-passau.de/bin/pic/logo.svg" style="width: 20px">
	or add tables <br><br>

	<table class="table table-hover"><tbody>
		<tr><td>Tab 1</td><td>10</td></tr>
		<tr><td>Tab 2</td><td>11</td></tr>
	</tbody></table>.

Special Characters
-------------------

=========== ============== ===============
Special     Name 		   Function Example
=========== ============== ===============
role1.png   Symbol Role 1  Red participant symbol |pic_role1| is displayed. 
role2.png   Symbol Role 2  Green participant symbol |pic_role2| is displayed.
$variable;  Variables      Beside normal text, you can also insert variables into the text box. If you have defined variables (see :ref:`Programming`), you can have these displayed by inserting the character "$", the variable name followed by ";". Make sure not to forget the ";" at the end! Variables and normal text can be combined.
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

.. image:: _static/elements/reference.png
    :alt:  300p

In order to avoid redundancies, you can reference elements and add them in a different place in the game (instead of copying them directly). For this, you can use the reference element. If the original element is altered, the reference is adapted automatically. The reference is created by selecting the stage number and the element number you are referring to. 

.. note:: If you require the same text in two stages, for example, an element reference is a far more elegant version than a simple copy because any changes to the original element are adopted automatically.

.. note:: Please notice that the display condition is not taken from the referenced element but  from the reference itself.

.. warning:: If you change the order of referenced elements, the reference does not automatically adapt, but has to be changed manually.

Program code
~~~~~~~~~~~~

Program snippets can be implemented to calculate results for each subjects. For further information see :ref:`Programming`.

.. image:: _static/program.png
.. role:: php(code)
   :language: php


Elements for participants
==========================

Input element
~~~~~~~~~~~~~

In this element, you can insert several input fields. These are numbered #1, #2, …. You can add input fields by clicking on *add new input field*. The input fields are displayed one after each other. Input elements always provide a submit button automatically. In the following, the different types of input fields are described in more detail.

The following settings are available for every input field: 

type of input 
	The type of input specifies why input should be taken by the input field, like numeric input, discrete choice, sliders, ...

variable name 
	The variable name is the identifier of the decision input. The variable is automatically stored in the subjects table. The variable name can then be used in programs. For example, if your variable is called $e, you can access it by writing "$e;" in a text box or use :php:`$e` in a program element. 

Furthermore, you can delete an input field by clicking on |pic_delete| or provide a display condition by clicking on |pic_display|. Display conditions are defined in the same way as for elements (see :ref:`Develop:Handling elements`).

.. |pic_delete| image:: _static/pic/reject.PNG
				:width: 15px

.. |pic_display| image:: _static/pic/show.png
				:width: 15px

.. warning:: Please notice that only one input element is allowed per stage. For several inputs add additional input fields to the first input element.

.. note:: In all fields, you can also use variables instead of numbers or text. This can e.g. be useful if you want to set a maximum depending on a variable :php:`$x`. Just enter $x; in the maximum field. This holds true for other fields as well.

Numeric input field
--------------------

.. image:: _static/elements/numeric.png
		:width: 49%
.. image:: _static/elements/numeric2.png
    	:width: 49%

The numeric input stores numeric input by participants and provides a basic check (minimum, maximum). It automatically rounds the input to a given decimal place and allows for input of digits with as :php:`2.34` or :php:`2,34`. classEx also automatically changes the input to numeric on mobile devices and shows the correct keyboard.

text
	The text is displayed on top of the input field. 

minimum
	The minimum specifies the minimal value. If the participant enters a value below the minimum a warning is displayed and he or she cannot proceed.

maximum
	The maximum specifies the maximal value. If the participant enters a value above the maximum a warning is displayed and he or she cannot proceed. (see figure)

digits
	The number of decimal places. classEx automatically rounds accordingly.

unit
	A unit (e.g. %, €, mm, …) can be specified that will be displayed on the right of the input field (here "years").

default
	A default value that is displayed to participants at the start. 

required
	This determines whether input is mandatory. In this case, participants cannot proceed without entering a value. 

output only
	This means that the field is read-only. Still, the value of the field is stored as normal variable. 


Buttons, simple list and drop list (single choice)
----------------------------------------------------

.. image:: _static/develop/buttons.PNG
   :height: 500px

This type of input is used for discrete decisions. You can implement single choice questions using buttons (left panel of figure below), simple lists (middle panel) or drop lists (right panel). This is what they look like in the participants' display. The settings are the same for these options.

.. image:: _static/ButtonsAndSelection3.JPG
    :width: 30%
.. image:: _static/ButtonsAndSelection2.JPG
    :width: 30%
.. image:: _static/ButtonsAndSelection4.JPG
     :width: 30%

text
	The text is displayed on top of the input field. 

default
	The default value is pre-marked at the start. For buttons it is highlighted with a color. For drop lists it is preselected.

required
	This determines whether input is mandatory. In this case, participants cannot proceed making a choice.

order of options
	The order of options can be set to *as stated* or to *random*. In the latter case, the random order is determined separately for each participant.

options
	Options can be defined in the lower area of the element. Participants make a decision by choosing one of the options. The order of options can be altered by clicking on the arrow. You can also delete or add options. 

	Options come with a displayed text and with a value. The value is stored in the data and as variable.

	You can mark the correct answer by clicking on the symbol |pic_correct|. In this case, if you use the single/multiple choice result element for the lecturer, the correct answer is marked there.

.. |pic_correct| image:: _static/pic/correct.PNG 
	:width: 15px



Checkboxes (multiple choice)
------------------------------

.. image:: _static/elements/multiple.png
		:width: 49%
.. image:: _static/elements/multiple2.png
    	:width: 49%

Choosing multiple options is possible by using checkboxes. Checkboxes work in exactly the same way as single choice options. Only the form of display is slightly different, as these are displayed as a list from which participants can pick several options. This way, multiple inputs can occur in one stage. Additionally to the single choice, you can specify the following settings:

minimum and maximum number of choices and 
	This restricts how many options can be picked by the participant.

number of answers per row
	This states how many options are displayed in each row (here 2).

.. important:: multiple choice inputs are stored separated with :php:`_`, e.g. :php:`2_3` if options with value 2 and 3 were selected. If you specify a default, please specify them accordingly. 


Radioline
---------

.. image:: _static/elements/radioline.png
		:width: 49%
.. image:: _static/elements/radioline2.png
    	:width: 49%

Radiolines, like Likert scales, offer stepwise input. Settings are

minimum and maximum
	The first bullet of the slider is the minimum value, the last the maximum values. For each bullet the value increases by one. In the example, a minimum of 0 and a maximum of 10 give 11 input possibilities.

default
	The default value is pre-marked at the start.

required
	This determines whether input is mandatory. In this case, participants cannot proceed making a choice.

label left and right of the slider
	You can add a label on the left and the right of the slider. Note that the values stated next to the labels are not used in the radioline.

Slider
------

.. image:: _static/elements/slider.png
		:width: 49%
.. image:: _static/elements/slider2.png
    	:width: 49%

Sliders are a similar concept. In this form of input, the participant moves a slider along a bar of predetermined positions. 

minimum and maximum
	The minimum and maximum determine the range of the slider.

number of steps
	The number of steps determines to how many position the slider can be moved. In the example, 20 steps between 0 and 10 mean that each step increase by 0.5. 

default
	The default value is pre-marked at the start. If no default is set, the slider is positioned in the middle of the bar.

required
	This determines whether input is mandatory. In this case, participants cannot proceed making a choice.

label left and right of the slider
	You can add a label on the left and the right of the slider. Note that the values stated next to the labels are not used in the radioline.

Text input
----------

.. image:: _static/elements/text.png
		:width: 49%
.. image:: _static/elements/text2.png
    	:width: 49%

Text input fields allow participants enter to a text. If a maximum is specified, it shows the number of remaining characters. 

minimum and maximum number of characters
	This limits the amount of characters which can be written by participants. 

default
	The default value is written in the text box.

number of rows 
	This determines the height of the text input field.


Hidden field
-------------

The hidden fields allows to save values. The only setting is to provide a default.


Next button
------------

The next button allows to add an additional button. Note that classEx normally provides buttons automatically. This may be useful, if you have no input but only a button. The only setting is the label of the button.


Other input fields
------------------

There are other input fields available (urn, infotext, mean of all input fields). This are outdated and should only be used with care.

The contract input field is also outdated. Please use the `Contract`_ element instead.

Additional settings
-------------------

.. image:: _static/elements/additionalsettings.png
    	:width: 49%


At the bottom of each input element you can find additional settings which open by clicking on *additional settings*.

button label
	Here you can specify the label of the button. The default is "Submit".

confirmation message
	If you enter a text here, participants are asked for confirmation before submitting. E.g. you can enter "Are you sure?" which is then displayed together with an OK button to participants.

hide decision after sending
	After submitting, participants see a confirmation message and their input. If you switch this setting on, the input is not displayed anymore after submitting.

directly to next stage
	Normally participants are moved to the next stage by the experimenter (see `Start Button and Automatic Start`_). If participants play individually and this settings is switched on, they move autonomously to the next stage. In this case, you have to select *no forwarding* if you use an automatic start.


show button later
	The appearance of the buttons can be delayed, e.g. if you want participants not to click too fast.





Winner's Notification
~~~~~~~~~~~~~~~~~~~~~

If a game is played with real payoffs, this element displays the payoff code to participants.  

.. image:: _static/Winner.PNG
    :alt:  300p

A winning notification is necessary for games with monetary payoff. The participants who are randomly drawn receive a winning notification as well as a code to cash in their earnings. 

Payoff(variable) in €
	The amount of earnings can be determined by this setting. You can enter a fixed amount or you can enter a variable that is calculated beforehand. If, for example, the variable :php:`$payoff` is calculated in a program during the game, you can enter :php:`$payoff;` in the earnings field.

You can adapt the message that is displayed in the winning notification. Clicking on the little info circles above the boxes will show you what will be displayed if you leave the boxes blank.

.. important:: The winning notification can only be displayed if you also define a (only works together with `Winner's draw`_) on the lecturer side. Otherwise no winner can be determined. Winners are always drawn with a lecturer element.


Contract
~~~~~~~~

.. image:: _static/rungame/seller_png.png
    :width:  100%
.. image:: _static/rungame/buyer_png.png
    :width:  100%

With this element, you can enable participants to conclude contracts. By adjusting the settings, you can customize the contract to your needs. Contracts can be used to trade a commodity between subjects in real time. Subjects move around in the classroom and talk to each other. When they agreed on a price, they enter it into the input mask together with the signature of the counterpart (see seller screen). The counterpart has to accept the trade (or reject it, see buyer screen).

The contracts made can be shown at the lecturer's screen with the `Contract table`_. In addition, there are special functions in globals and subjects programs to retrieve contracts (see :ref:`Programming`). All contracts are also stored in the standard excel file which can be retrieved in the data menu. 


.. image:: _static/Contractparticipant.JPG
    :alt:  300p

Contracts can be set up by adding contract elements **both for buyers and sellers**. 


sell offers/buy offers
	If you turn this on, you allow for sell or buy offers made by the respective subject.

set quantities
	allows to set quantities (otherwise quantity is always 1). With quantities, prices are set as price/unit.

no signature
	allows to disable the signature. The signature is needed for sell and buy offers to be send to a specific person. E.g. if the buyer can make buy offers, she needs the signature of the seller to send the offer to.

max # contracts
	Maximum number of (accepted) contracts limits how many contracts can be made by a subject.

currency/min price/max price/decimal place
	Currency of the prices and minimum, maximum and decimal places can be specified here.

maximum quantity
	Maximum quanity a subject is allowed to possess limits how many items can be bought.

products
	You can specify a name (or a small image) and the initial amount of the good (e.g. the seller has 1 unit, the buyer 0 units).

Payoff Matrix Game
~~~~~~~~~~~~~~~~~~



.. image:: _static/elements/matrix1.png
    :width:  49%
.. image:: _static/elements/matrix2.png
    :width:  49%



This element helps display the payoff from a two role game easily. This provides a simplification instead of using subjects programs to retrieve the other participant's value and to calculate payoffs. The same can be achieved with text boxes and subjects programs.

decision role 1 and role 2
	You need to specify which input field contains the decision of the respective participant for the row participant and for the column participant. The labels of the payoff matrix are determined by the specified input fields. 

results matrix
	In the table, you enter the payoff for the row participant first followed by the payoff for the column participant. The payoff is stored as variable $payoff; which can then be used for the winning notification or further calculations.


Camera
~~~~~~

.. image:: _static/Camera1.PNG
    :width: 100%
.. image:: _static/Camera2.PNG
    :width: 49%

With this element, you can enable participants take a picture of themselves.

variable
	The variable name, under which the picture is stored, has to be defined. 

allow retake
	Additionally, you can define if participants are allowed to retake a picture. Then only the last picture taken is saved.


.. note:: Informed Consent: Participants are asked by the browser if the browser can access the webcam or not. Please make participants aware that they do not have to take a picture and ask them for their consent.

Retrieving Pictures
-------------------
Pictures can be retrieved in the following ways:

At the participant' screen
	You can use the normal variable notation ($image;) to display pictures in textboxes.

At the lecturer screen
	You can use :php:`$getValues(...)` to retrieve the pictures of all participants and display them (see :ref:`Programming:Functions`).

From the stored data
	In the downloaded data you find stored images in the subjects table. They can are base64 decoded and can be encoded with free online tools. Just take away "data:image/jpeg;base64," from the string, so that it starts e.g. with "/9j/....".

Javascript program
~~~~~~~~~~~~~~~~~~~

You can also add small javascript programs to the participant screen. More information can be found at :ref:`Programming:Javascript`.

Filled in form 
~~~~~~~~~~~~~~

This element allows you to display the filled in input element of the previous stage. This element is outdated and should only be used with care.

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

button label
	You can name the button (e.g. Start Trade).
feature
	Instead of starting the current stage, you can also use the start button to jump to different stages. 
confirmation message
	You can set if a pop-up should appear after clicking to confirm the action. 
count
	You can set the counter which appears after the start button is clicked. It can count decisions (also by role, treatment or group if set). 

Automatic Start
---------------

.. image:: _static/Automaticstart.PNG
    :alt:  300p

The automatic start button allows you to start stages when subjects finished the previous stage.

mode
	The mode can be set to:

	- start if possible: If a subjects finishes the previous stage, it is forwarded to the next stage.
	- wait for all: Subjects are only forwarded if everyone in the group is done with the previous stage.
	- no forwarding: Subjects are not forwarded (This feature is only used if subjects forward them self by clicking on a button. This can be set in additional settings of the input element).

count
	You can set the counter which appears after the start button of the previous stage is clicked. It can count decisions (also by role, treatment or group if set).

counter
	Setting this additionally allows you to deactivate the counter completely.



Winner's Draw
~~~~~~~~~~~~~

.. image:: _static/Draw.JPG
    :alt:  300p

This element should be implemented in the last stage and draws a winner from among all participants. The earnings should be calculated individually on the participant side (see `Winner's notification`_ for participants). You can determine whether single participants or coupled participants shall be drawn. Drawing coupled participants only makes sense if you have defined roles. You can also decide how many winners you want to draw.

.. important:: Payoffs per game are restricted to 100€ per default. If you need higher payoffs, you have to overwrite the variable $maxWin in a global program (e.g. :php:`$maxWin=1000;`).

.. note:: For games with two roles it is advisable to draw coupled participants as winners because the possibility that only one of the two participants could be drawn might overshadow considerations of fairness or reciprocity. Experience has shown that earnings of less than 5€ are usually not cashed in. Therefore, games should be calibrated in a way that ensures that earnings are at least 10€.

.. important:: Winners are only drawn from participants who made a decision to avoid inactive participants to be drawn. Therefore it does not make any sense to put the winners' draw in the first stage.**

You should draw winners only once in a game as the payoffs codes do not distinguish between rounds.

Lecturer Discrete Choice
~~~~~~~~~~~~~~~~~~~~~~~~~

.. image:: _static/Randomdraw.PNG
    :alt:  300p

With this element the lecturer/experimenter can make decisions for all participants during the game, e.g. tossing a coin in front of the class and entering the value in classEx so that payoffs can be calculated based on the coin toss.


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

In the contract table you have several tabs where you can jump between. You can see them in the pictures on the right hand side.

contracts
	lists all contracts made.

on average
	yields overview statistics for each round (mean, median, min, max, std dev)

chart
	show contracts made over time. In case of different quantities it also shows a bubble chart for the combination of quantities and prices.

predicition
	shows a predicition (if set). To create a prediction the variables $demand and $supply have to be filled in a global program. $supply and $demand should be arrays which contain prices as index and the resulting quantity as a value.

You can make the following settings.

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

Whenever you can select variables in a field you only need to insert the variable name (e.g. "payoff"). All other input fields require the usual notation (e.g. "$payoff;").

Under the setting *count*, you can determine whether results shall be displayed separately for groups, treatments or roles (if defined). 

Results Single / Multiple Choice Questions
------------------------------------------

.. image:: _static/Smc.JPG
    :alt:  300p

The results are displayed with percentage bars.

.. image:: _static/Singlechoice.PNG
    :alt:  300p

The following settings can be changed:

count
	Participants are counted all together (or per treatment / role).
show element
	Always display element or only if stage is activated.
input
	The variable which should be displayed (here: stage #1 input field #1). 

The element automatically detects if the input is multiple choice or single choice. Hovering over the bars gives the absolute frequency of participants who opted for that option. The element should only be used with input fields with predefined options (otherwise you should use the counter result element).

Results Histogram
------------------

.. image:: _static/Numberindic.PNG
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


.. note:: All values that are larger than the displayed maximum value are automatically pooled into the last bin.

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

Using a multiple choice input field will result in the listing of combined answers. E.g. You can select A, B, C (multiple choice). Then the counter element will display who many percent chose A, A&B, A&C,... If you want to have the items analyzed separately (only A, B, C) you should use the Results Single / Multiple Choice Questions (see above). 

Results Game Matrix
--------------------

.. image:: _static/Qqq.JPG
    :alt:  300p

.. image:: _static/Qq.JPG
    :alt:  300p

If a game is played with two different roles, the results can be displayed as a matrix. The settings are the same as for the participant screen. If you have defined treatments, you can decide whether the results shall be displayed per treatment or altogether.

If you have several rounds, the matrix calculates the results overall rounds. If you want to show temporal structures (e.g. learning), please use the time line diagram.

.. note:: The displayed matrix only determines the image on the lecturer’s screen and not the payoff for participants. The payoff is calculated individually for the participants (either through the element "payoff for 2 roles" or through a program).

Other result elements
----------------------

Other result elements include Likert scales and pie charts. They will be documented soon.

