===========
Programming
===========

.. role:: php(code)
   :language: php

Programs are a very useful to design dynamic games. Programs are elements of stages and therefore created like any other element (see :ref:`Develop:Define Elements`).

.. image:: _static/program.png

There are two types of programs, subjects and globals. Subjects programs are executed for each participant, global programs are executed once for all participants.

.. note:: It is always good to comment the code if you try to understand it later. Add comments with :php:`/* comment */` to your program code.

Programming language 
====================

Variables and programs are specified via `PHP <https://en.wikipedia.org/wiki/PHP>`_. Currently, we use PHP 7.0. This is a well-documented standard which enables easy programming. Details can be found in the internet, for example `here <http://php.net/docs.php>`_. You can utilize the normal standard PHP functions (e.g. :php:`round(), rand(...), number_format()`,...).

Programs are entered in an editor that comprises syntax-highlighting as well as a simple error check of the entered codes.

Furthermore, the editor contains a completion system which will show you all available variables. If you start entering the beginning of a variable ($...) and then press Ctrl+space the automatic completion system will show you all corresponding variables and functions.

.. warning:: You can not declare own PHP functions in classEx.


Declaration of variables
========================

Variables are defined by starting with :php:`$`. It does not matter whether the variable is a number or text. Variable names are case sensitive.

.. code:: php
	
	/* numeric variable */
	$endowment = 10;

	/* string variable with a varialble */
	$info = "Your endowment is ".$endowment." Euros.";

	/* array */ 
	$values = array(1=>"one", 2=>"two", 3=>"three");

.. warning:: Do not use single quotes within double quotes as this may produce errors (e.g. $text="don't"), instead of ' you should use the HTML code &apos; (e.g. $text="don&apos;t") in texts.

Scope of variables
==================

There are two different scopes: globals and subjects variables. 

Globals variables are

- available for all participants (can be accessed by subjects program),
- are calculated at the lecturer side,
- are the same for every participant,
- are calculated first (i.e. before subjects variables).

Subjects variables are

- only available for a specific participant
- saved by default if they are decision variables (set via input elements).
- not saved by default if you create or calculate them in subject programs; to do so use the `Function to save variables`_

.. note:: Please notice that globals and subjects variables share the same namespace. Using the same variable name may overwrite variables. E.g. if you define :php:`$payoff=1;` as a globals variable, and :php:`$payoff=2;` as a subjects variable, the first will be overwritten by the latter as globals are executed first.

.. note:: Subjects variables are only available to a specific participant. This means if you want to use the decision of one participant in another's screen, you have to use the functions below to retrieve the decision (e.g. from the partner or group member). You can also retrieve decisions as a globals variable (which then are available to all participants) and retrieve the globals variable for a specific participant.


Execution, Synchronization and Lifetime 
========================================

Execution
~~~~~~~~~

Variables and program code is always executed in a sequential order. This means that elements which come first are executed first. 

The overall order is the following:

- First, parameters are set as globals variables (see also :ref:`Develop:Parameters`).
- Second, globals programs are executed (in the order stated for the lecturer screen).
- Third, subjects programs are executed (in the order stated at the participant screen).

Subjects programs offer the option to delay them after the decision has been made. The provide the setting *execute only after input*. This means that the subjects program is not executed on the loading of the respective screen, but only after a participant submitted his or her decision. 

.. note:: This feature can be useful if you want to do some calculations with the current input before the next stage has started. You can e.g. add to inputs :php:`$a` and :php:`$b` and safe them as a new variable with :php:`$save('sum',$a+$b)`. Logically, this can only be done, once the inputs are provided. In some cases, it might be useful to have the sum already available in the next stage (e.g. to display the sum in a graph).

Synchronization
~~~~~~~~~~~~~~~

It is always important to keep in mind how synchronization works in classEx in order to retrieve variables at the correct moment in time. Within one stages, participants make their decisions (and therefore create their input variables) at any point in time. So you do not know if the value has been set or not. For this reason, you should only retrieve values in the following stage. 

E.g. if you want to display the input :php:`$a` of participant A to another participant B, you can only use :php:`$other = $findVariablePartner("a");` only in the next stage and not in the current one. It may be the case that A has not made his or her decision while B is trying to retrieve it. The same holds true if you want to display the input :php:`$a` in a result graph or do some calculations with it in a globals program.

One exception is the usage of *execute only after input* in the section `Execution`_. This allows to do some calculations after the input of a participant. Still, keep in mind, that you do not know when this program will be executed as the participant may submit his or her input at any point in time.

Another exception is that you can repeat globals programs every 2 seconds. This can be set by selecting *update every 2 s* next to the program element. Then the program is executed every 2 seconds and calculations are updated. This allows to get input decisions in real time.

Lifetime
~~~~~~~~~

Variables and their values can be used after their declaration during the whole game. They can be read and overwritten at any point after their declaration. 

Subjects values can only be changed by subjects programs and globals values only by globals programs.

If you e.g. set :php:`$a=1;`in stage 1 (as a globals variable), you can use this value in all stage after stage 1 as well. Keep in mind that for subjects variables this only holds true for the participant's own variables.


Description of functions in the documentation
==============================================

Functions are described in the following way. It follows the standard way of documentation of functions. Let's take the following example:

.. code:: php

 $findVariablePartner("varname", $round = $currentRound, $partnerRole = null, $no_decision = null);


Function name
 	The name of the function is *$findVariablePartner*. 

	.. note:: Notice that in contrast to standard PHP function, internal functions in classEx always start with a $ sign. 

Arguments
	A function has arguments which are the values the function is called with. In this case, the function has four arguments. The first argument is mandatory, the other three arguments are optional. Arguments can be strings, numbers or variables.

Arguments without default value (mandatory)
	Arguments which are not marked with a "="-sign and a default value are *mandatory*. This means you have to specify them in order to make the function work. In the example, you have to specify the variable name "varname". The quotes indicate that you have to specify it as a string. 

	.. note:: Note that variables names in functions are specified without the $ sign.

Arguments with default value (optional)
	All the other arguments in the function have default values which means that they are optional. You can specify the function with only one parameter as well. As default the values after the "="-sign are taken. In the example, the variable $currentRound (which is available as pre-defined global variable) is taken as default for the round. If you want to use a different round, you have to overwrite the default value. The same holds true for the other arguments. $partnerRole and $no_decision are set to *null* as a default, where *null* means no value.

	Here are some examples:

.. code:: php

	/* This gives the value of the third round. */
 	$findVariablePartner("varname", 3);

 	/* This gives the value of the previous round. */
	$findVariablePartner("varname", $round - 1);

	/* This gives the value of the current round for partner role 2. */
	$findVariablePartner("varname", $round, 2);

	/* This gives the value of the current round and return 0 in case of no decision. ($partnerRole is set to its default.) */
	$findVariablePartner("varname", $round, null, 0);


.. note:: If you want to change some of the default values in arguments at the end of the function, you also have to specify the arguments before the argument you want to change. You can see this in the last code example where want to leave $partnerRole on its default value and only change $no_decision.




Variables for participants (subjects)
======================================

Pre-Defined Variables
~~~~~~~~~~~~~~~~~~~~~~

============== =========
Variable Name  Value
============== =========
$lang          Actual language (0: German, 1: English, 2: Spanish)
$round         Current round
$id            participant ID (unique in all games, decisions are stored with the participant ID)
$subject       Subject ID (unique in game, starts from 1,...)
$role          Role ID (if set)
$treatment     Treatment ID (if set)
$group         Group ID (if set)
$signID        Private signature (for contracts)
$tic           External ID (if set at login or provided with URL)
============== =========

The variables $group, $role and $treatment can be overwritten in a subjects program.

.. note:: Pre-defined variables are not saved automatically in the subjects table. Therefore, they can only be retrieved with e.g. $findVariablePartner(...), $getValues(...) or other functions if they are saved before.

Functions to retrieve variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following functions can be used to retrieve variables. If you want to access the name of a variable, you put the name in quotation marks. If you want to access the value of a variable, you add a $ in front of the variable name. 


=========================================================================================== ================================================= ==============
Function name                                                                               Calculates                                        Returns
=========================================================================================== ================================================= ==============
$findVariablePartner('varname', round=currentRound, $partnerRole=null, $no_decision=null);  Returns the decision of the partner               Variable value
$findGroupAverage('varname',round=currentRound,includingOwn=false);                         Average of a variable per group                   Array with group number as index
$findGroupSum('varname',round=currentRound,includingOwn=false);                             Sum of a variable                                 Sum as number, 0 otherwise
$findGroupFreq('varname',round=currentRound,includingOwn=false);                            Frequency of specific decisions by group members  Array with frequency of each decision
$findSold(round = currentRound)                                                             For a contract table: finds sell                  Array with number of unit (1,2,...) and corresponding price
$findBought(round = currentRound)                                                           For a contract table: finds buy                   Array with number of unit (1,2,...) and corresponding price
=========================================================================================== ================================================= ==============

Here are examples of all mentioned funtions:

.. image:: _static/Code1.PNG
    :alt:  300p



The elements of the functions mean the following:

varname
	here, you need to enter the name of the variable you want to retrieve, for example 'price'

round = currentRound
	this means that the default is set to the current round. If you want to access the variable of a different round, you must enter the round in the function. If you want to set the round to the current round (you need to do this if you add another parameter behind the round), you simply write $round in the expression.

includingOwn = false
	for averages, sums and frequencies, you can decide whether you want to include the own value or not. The default is set to *false* which means that values are calculated over all other subjects, excluding the own value. If you want to include the own value, you need to enter *true* in the function

$partnerRole = null
	if you only have two participants in a group, the other participant is automatically the partner. However, you can specify which partner is meant if you have more than two participants in one group. To specify a participant, just write the role number in the expression.

$no_decision = null
	this means that the default is set that if the partner has not made a decision and you try to access it, the function gives you null.


	IMPORTANT NOTICE: If you want to add an element that, for example, is placed at the third position in the function, you have to specify the elements before that, too. Otherwise, the element is used at the wrong position for the wrong expression.



Function to save variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To save calculated variables you must use the following function:

**$save('varname', value);**

The elements of the function mean the following:

varname
	enter the name as which you want to save the calculated variable

value
	enter the value which should be saved for it. Here, you can insert a variable such as $price; or a calculation such as 10-$price

Here is an example:

.. image:: _static/Code2.PNG
    :alt:  300p

Variables for lecturers (globals)
=================================

Pre-defined variables
~~~~~~~~~~~~~~~~~~~~~~

============== ============
Variable       Name Value
============== ============
$lang          Actual Language (0: German, 1: English, 2: Spanish)
$currentRound  Current Round
============== ============

Functions
~~~~~~~~~~

The following functions can be used to retrieve global variables. Here is some additional information on the structure. If you want to access the name of a variable, you put the name in quotation marks. If you want to access the value of a varible, you add a $ infront of the variable name. The elements of the functions mean the following:

varname
	here, you need to enter the name of the variable you want to retrieve, for example 'price'

round = currentRound
	this means that the default is set to the current round. If you want to access the variable of a different round, you must enter the round in the function

======================================================== ====================================================================================================================================== ====================
Function name                                            Calculates                                                                                                                             Returns
======================================================== ====================================================================================================================================== ====================
$getAverage('varname',round=currentRound);               Average of a variable                                                                                                                  Average as number, 0 otherwise
$getAveragePerRole('varname',round=currentRound);        Average of a variable per role                                                                                                         Array with role number as index
$getAveragePerTreatment('varname',round=currentRound);   Average of a variable per treatment                                                                                                    Array with treatment number as index
$getAveragePerGroup('varname',round=currentRound);       Average of a variable per group                                                                                                        Array with groupnumber as index
$getVarSum('varname',round=currentRound);                Sum of a variable (also available getVarSumPerGroup, getVarSumTreatment, getVarSumPerRole)                                             Sum as number, 0 otherwise
$getMin('varname',round=currentRound);                   Minimum of a variable (also available getMinPerGroup, getMinPerTreatment, getMinPerRole)                                               Minimum as number, 0 otherwise
$getMax('varname',round=currentRound);                   Maximum of a variable (also available getMaxPerGroup, getMaxPerTreatment, getMaxPerRole)                                               Maximum as number, 0 otherwise
$getFreq('varname',round=currentRound, multiple=false);  Frequency of a variable value (if multiple is set to true, answers from multiple choice questions are decomposed into single answers)  Array with the variable value as index
$getValues('varname',round=currentRound);                Single values for each participant                                                                                                          Array with the participant number as index and the corresponding value
$getRoles();                                             Role for each participant                                                                                                                   Array with the participant number as index and the corresponding role
$getTreatments();                                        Treatment for each participant                                                                                                              Array with the participant number as index and the corresponding treatment
$getNumRoles();                                          Number of roles                                                                                                                        Array with role as index and the number of participants who have this role
$getNumPlayer();                                         Number of participants                                                                                                                      Number
$getSubjectIDs();                                        Get Corresponding Subject IDs to participant IDs                                                                                            Array with participant ID as index and subject ID as value
$getNumDecisions('varname',round=currentRound);          Number of decisions made                                                                                                               Number
$getNumDecisionsPerGroup('varname',round=currentRound);  Number of decisions made                                                                                                               Array with Group Number as an index
======================================================== ====================================================================================================================================== ====================

Here are examples of all mentioned funtions:

.. image:: _static/Code3.PNG
    :alt:  300p

Debugging
~~~~~~~~~

Small errors can cause the programs not to run. Therefore, error detection is an important issue. First, have a look in the editor which provides a basic syntax checking. Errors are marked by red crosses. If the program is running but not performing in the expected way, you may use the diagnosis mode to find the error.

With severe errors the lecture mode can not be started. In order to find the error go through the code and look for errors. Check if the function names are correctly spelled.

Diagnosis tool
--------------

The diagnosis mode is very useful for trouble shooting and testing your game. You can access the diagnosis mode by clicking on the stetoscope icon in the top bar of the lecture mode.

.. image:: _static/Diagnosissteto.PNG
    :alt:  300p

Clicking on the symbol opens up a space beside the usual display on the lecturer's screen, which shows you all variables and their current values.

.. image:: _static/Diagnosis.PNG
    :alt:  300p

The different tabs allow you to access the globals or the variables for each participant. This makes it much programming and error finding much easier than having to jump back and forth between the lecture mode and the editing mode.

