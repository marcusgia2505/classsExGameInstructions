===========
Programming
===========

Programs are a very useful to design dynamic games. Programs are elements of stages and therefore created like any other element (see `Adding elements`_).

.. image:: _static/Code.JPG
    :alt:  300p

You can define for which roles, groups or treatments (if defined) the code shall apply to by choosing the corresponding option from the drop down menu above the code. Or you define a display condition which determines if the program is executed.

.. note:: It is always good to comment the code if you try to understand it later. Add comments with /* comment */ to your program code.

Programming language and editor
================================

Variables and programmes are specified via `PHP <https://en.wikipedia.org/wiki/PHP>`_. This is a well-documented standard which enables easy programming. Details can be found in the internet, for example `here <http://php.net/docs.php>`_. You can utilise the normal PHP functions (e.g. round(), rand(...), number_format(),…).

Programmes are entered in an editor that comprises syntax-highlighting as well as a simple error check of the entered codes.

Furthermore, the editor contains a completion system which will show you all available variables. If you start entering the beginning of a variable ($...) and then press Ctrl+space the automatic completion system will show you all corresponding variables and functions.

Declaration of Variables
========================

Variables are defined by starting with "$". It does not matter whether the variable is a number or text. Variable names are case sensitive.

**ATTENTION! Do not use single quotes within double quotes as this may produce errors (e.g. $text="don't"), instead of ' you should use &apos; (e.g. $text="don&apos;t") in texts.**

Scope of Variables
~~~~~~~~~~~~~~~~~~~

There are two different scopes: globals and subjects variables. 

Global variables are

- available for all participants (can be accessed by subjects program),
- are calculated at the lecturer side,
- are the same for every participant,
- are calculated first (i.e. before subjects variables).

Please notice that globals and subjects variables share the same namespace. Using the same variablename may overwrite variables.

Subject variables are

- only available for a certain participant
- saved by default if they are decision variables (set via input elements).
- not saved by default if you create or calculate them in subject programs; to do so use the `Function to save variables`_

Variables for Participants (subjects)
======================================

Pre-Defined Variables
~~~~~~~~~~~~~~~~~~~~~~

============== =========
Variable Name  Value
============== =========
$lang          Actual Language (0: German, 1: English, 2: Spanish)
$round         Current Round
$id            participant ID (unique in all games, decisions are stored with the participantid)
$subject       Subject ID (unique in game, starts from 1,...)
$role          Role ID (if set)
$treatment     Treatment ID (if set)
$group         Group ID (if set)
$signID        Private Signature (for contracts)
$tic           External ID (if set at login)
============== =========

The variables $group, $role and $treatment can be overwritten in a subjects program.

Functions to retrieve variables
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The following functions can be used to retrieve variables. Here is some additional information on the structure. If you want to access the name of a variable, you put the name in quotation marks. If you want to access the value of a varible, you add a $ infront of the variable name. The elements of the functions mean the following:

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

