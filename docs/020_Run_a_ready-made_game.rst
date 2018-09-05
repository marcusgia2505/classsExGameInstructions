=====================
Run a ready-made game
=====================

.. youtube:: zmAn0ZzTQPk
   :height: 315
   :width: 500
   :align: center

Prerequisites (students devices, lecturer device, data volume)
==============================================================

- Students devices

Every student who wants to participate in a session needs a mobile device (e.g. mobile phone or tablet) with a browser and internet connection.

- Lecturer device

The lecturer conducting a session needs a device (e.g. laptop, tablet) with a browser and internet connection. The screen of the lecturers device should be visible for all players (e.g. via a classroom projector).

- Data volume

classEx only requires a small amount of data volume. When using classEx as a player for the first time, loading all settings requires about 120 KB (this is cached and does not need to be reloaded when reentering). Each game that is played requires data volume of roughly 20 KB. 

Practical tips
==============

The following hints should give you some advice to avoid problems when using classEx especially the first time.

- Information upfront for students (e.g. via email)

  - Students have to bring a device that has internet access to class, preferably a smart phone, but a tablet or laptop computer also work.

  - The devise has to have enough battery left (suggest to bring a charger).

  - The browser they use should be up-to-date.

- Before the course

  - Make sure that you are not logged into your account on another computer (e.g. in your office). You can not log into the system from two different computers at the same time.

- Before you start

  - Make sure you have a stable internet connection as a lecturer. The best option is with a cable.

  - It is best not to use the same connection (e.g. wifi) as the participants in case the network slows down.

  - The ideal browser to use is Mozilla firefox (in a current version). Javascript has to be turned on and cookies allowed (normally default setting).

- Information for students in the course

  - Students need to stay logged in until the experiment is over.

  - Students need to close all the apps. Having other apps open might log students out.

  - If the experiment has already started (and some decisions have already been entered), students might not be able to join the experiment any more.

  - If students are chosen randomly to receive their payoff, they should screenshot their winner's notification to be sure to receive their payoff.

- During the experiments

  - If you accidentally close the browser, no problem. Just open it again. Normally you should be still logged in. Otherwise just log in again.

  - In case you want to logout all participants, just press the logout all participants button in the "course data" section.

  - Note that there is no way back if you continue to feedback or next round/session.

  - If your game has several rounds / stages, make sure to stay in the first round long enough, as this is where students are matched.

- After the experiment

  - You can download the excel files containing the data of the game.

  - If you want to go back to compare the current results with old ones or ones in different courses, click on “previous results”.

- Password forgotton

If you have forgotton your password, you can simply click on the little "get a new password" button underneath the login button. You only need to enter your email address with which you registered. 

Login of participants and test participants (+logout)
=====================================================

- Login

.. image:: _static/Loginnnn.JPG
    :alt:  300px

In order to login, participants go to the website http://classex.uni-passau.de and choose their university and then their course or lecture. They enter the password provided by the lecturer and click on "Login".

.. image:: _static/Noopenvotings.JPG
    :alt:  300px

If participants are logged in before the lecturer has started the game, participants see a waiting screen. The lecturer can edit the text on the waiting screen in the Editing Mode in “own data”.

- Login with QR-Code

All experiments can be accessed by participants via a QR-Code. This QR-Code is provided automatically in the Lecture Mode on top of the page. Enlarge the QR code by clicking on the symbol.

.. image:: _static/QRlogin.PNG
    :alt:  300px

Lecturers can either copy the QR-Code and print it on flyers, for example, or display it on the screen. When clicking on the QR code symbol instructions how to log in without using the QR code also appear on the screen.

- Personalised login with ticket

You can provide players with a personalised ticket to log-in to classEx. This way you can ensure that players only take part on one device and also track the actions of specific participants. You simply need to add &tic= to the URL. The ticket is saved to the player data and can be retrieved as $tic; in the game. 

- Add/login test player

As lecturer you can run a game with fictional test players. To add a test player click on the button in the lecture submode menu:

.. image:: _static/Addplayer.PNG
    :alt:  300px

For every added test pa new tab in your browser will open. The tab for a test player replicates the fully functional interface for a real player. This enable you to make test runs which is especially useful when you develope your own games.

- Logout

Currently, there is no logout button for participants. Participants can log out by adding *?logout* at the end of the web address. As a lecturer you can log out all participants that are currently logged in to your class by going into your course data and clicking on this button: 

.. image:: _static/Bigredbutton.PNG
    :alt:  300px

- Refresh Page

Participants’ screens are updated automatically when their partner has made a decision or when the lecturer has started a new stage. Therefore, it is not necessary to press a refresh button to proceed. This way, participants can simply wait until the next stage appears on their mobile devices and do not have to keep refreshing their screens. 

Run a game (mit 2 Bsp., parameters, neu starten)
================================================

- Start a Game

During a lecture, the interaction between the lecturer and the players takes place in the lecture mode. The lecturer’s browser is usually projected to a wall. Games are started and terminated in the lecture mode and the results are also displayed in this mode. The lecturer can start this game or select a different one.

The lecturer can select a new game by choosing it from the drop down list. The drop down list shows all available games. A selected game can be started by pressing:

.. image:: _static/Startblue.JPG
    :alt:  300px

By pressing start, the lecturer initiates the first stage of the game. If a game consists of several stages, the start button for the next stage appears after pressing the start button for the first stage.

The counter over the start button shows how many participants are currently logged in. There is no minimum number of players required to start a game.

If a game consists of several treatments and / or roles the participants will be placed into treatments / roles alternately. If the number of players is not a multiple of the group size, the programme code FindPartnerDecision (see Elements) can be equipped with a random argument, so that no players are excluded from the game.

- During the Game

During the course of a stage, a display shows how many participants are logged in and how many of them have already made their decision in the current stage.

.. image:: _static/Displres.JPG
    :alt:  300px

Here, 3 participants are logged in and 1 has already made their decision.

    Tip: If you play a game with large groups, it can happen that participants take some time until they make their decision. You should wait for a while but then terminate the input phase and carry on if the added value of more input is fairly small.

- End the Game

When the participants have made their decisions, the lecturer can end the game by clicking on „display results“.

.. image:: _static/Dispay.JPG
    :alt:  300px

If games are played for real money, the lecturer does not only have the normal „display results“ button but also the enhanced button "Display results and payoff". If you should not want to pay out any money, for example in a practice round, you have the possibility of clicking on “display results only” below the actual button. 

- Change parameters

You can now change the parameters of a game by clicking on |Para|. For example, in a public goods game, you can change the MPCR, the endowment and the amount of rounds and restart the game with the new settings. You can restart the game by clicking on |Rere|. 

.. |Para| image:: _static/Para.JPG
.. |Rere| image:: _static/Rere.JPG

Players interface
=================

The players interface should be self-explanatory. The most common actions players are asked to carry out are binary decisions and numeric decisions.

- Binary Decisions

.. image:: _static/Binarydecision.JPG
    :alt:  300px

When a game has been started, the first decision is shown along with the role of the particpant |Role1|. By clicking on one of the options, the decision is submitted and saved.

.. |Role1| image:: _static/Role1.PNG

- Numeric Decisions

.. image:: _static/Workinghours.JPG
    :alt:  300px

Numeric decisions can also be made by entering a number and pressing the submit button. If the input exceeds a predefined maximum or minimum, the participant has to redo his or her input. Beside minima and maxima you can also specify the number of digits and whether entering an input is mandatory. For further information see Elements.

- Other Decision Types

There are other input types such as radio buttons or sliders which are explained in the section Elements. 

Simple quiz question
--------------------

Two player game
---------------

Trading game
------------

Disbursal of payoffs
====================

In some games participants will receive a monetary payoff. The payoff is managed by providing the participant with a payoff code. Participants should not show their payoff code to others, as others could then claim the payoff. Therefore, it is advisable for participants not to let any other participant see the screen of their mobile device during the experiment.

.. image:: _static/Payoffff.JPG
    :alt:  300px

The lecturer reserves the right of withholding the payoff in the event of error. The participant can present the payoff code to the administrative staff after the end of the lecture in order to claim his or her payoff. The person entrusted with disbursing the payoff can log-in into the adiministration mode by selecting it in the drop down menu.

.. image:: _static/Adminmode.JPG
    :alt:  300px

The administrator then sees a screen indicating the date, the payoff code and the amount of money to be paid out to the participant. Further, clicking on the red icons opens up pdf of a receipt that must be printed out and then signed by the participant. Also, the administrator must tick the box on the right indicating that the participant has picked up his or her payoff.

.. image:: _static/Payout.JPG
    :alt:  300px

Graphical results
=================

.. image:: _static/Beautymacro.JPG
    :alt:  300px

Some of the displayed figures and graphs can be adapted. All figures that are labelled with Highcharts.com (see bottom right corner of the figure above) have a zoom function. You can zoom in by simply clicking and pulling the mouse over the section you want to zoom in on. The button “Reset zoom” resets the display back to the original size.

For histograms, you can also change the settings for the bins and the maximum by clicking on the little symbol under the bottom left corner of the chart. You simply change the values in the fields and then click beside the bins display. This can be useful if the default bins’ size was too small (the bins are then changed for all graphs).

In the top right corner of the graph, you can see a symbol with three lines. Clicking on this symbol allows you to download the graph in different formats (jpeg, png, pdf, svg). You can also print the graph.

Via the button "previous results" in the lecture submode menu you can also access and display results of previous sessions.

For the different result graphs see Result elements in Elements. 

Dealing with problems (logout, playerNr)
===============================================

