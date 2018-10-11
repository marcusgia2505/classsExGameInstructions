.. _basic:

======
Basics
======

Registration
============

Lecturers who want to actively involve their students are required to register in order to use classEx. Please fill in the registation form you can find `here <https://classex.de/get-login-credentials/>`_. Registered users receive a password via e-mail and hereby obtain the right of unlimited and cost-free use of classEx for teaching, further education and research (for details please see `terms of use <https://classex.de/wp-content/uploads/2018/04/TermsOfUse.pdf>`_). Students do not need to register but are involved anonymously in lectures and presentations.

Login
=========

.. image:: _static/Login.PNG
    :alt:  200px

The website https://classex.uni-passau.de displays an input screen to lecturers and students.
First of all, the institution needs to be selected. Next, the course needs to be chosen.
Lecturers (experimenter/lecturer), students (player) or individuals entrusted with the payoff
(administration mode) chose their corresponding user type, enter the password and log in.

Institution
    Select the institution you named during your registration, typically your university.

Course
    Select the course you named in your registration or another course you have access to.

User modes
    - Player: Students can participate interactively in a lecture or a presentation by logging in as a “player”. They do not need to register and remain anonymous. They select the university and the course from the lecturer's registration. The lecturer provides the password he has chosen for players in his course. Participation after logging in is self-explanatory and does not require any previous knowledge.

    - Lecturer: Registered lecturers who have received a password can login as "lecturer". As lecturer you can organize your account, start ready-made games and quizzes, adapt them to your liking or create new ones. This documentation mainly explains the possibilities and options classEx offers for lecturers.

    - Administration mode: Individuals entrusted with the payoff can enter the administration mode in order to disburse the monetary payoff. This task can be delegated to a trustworthy person by the lecturer. You can find further instructions `here <https://classex-doc.readthedocs.io/en/latest/020_Run_a_ready-made_game.html#payoffs-and-administration-mode>`_. 

Password
    A registered lecturer receives has received a password upon registration. Players are provided with their password by the lecturer. Administrative staff ???

Essentials for lecturers
=========================

.. raw:: html

    <div style="text-align: center; margin-bottom: 2em;">
    <iframe width="100%" height="350" src="https://www.youtube.com/embed/oJsUvBQyHBs?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>

A short introductory tutorial can be found under `here <https://youtu.be/Zm0DpUzhOGg>`_.

Entering classEx as a lecturer offers three modes: Overview mode, Lecture mode and Editing mode. The after login the screen shows the Overview mode. Here you can organize your games and access all important features of classEx.

.. image:: _static/Overview.PNG
    :alt:  300px

Navigation bar
--------------

In the top right-hand corner, you find the main navigation bar which is always displayed in every mode. This allows you to switch from one mode to another and access your personal data.
    
The currently active mode is marked by a darker shade around its symbol, here the **Overview mode**. The left symbol takes you to the **Lecture mode**. The right symbol takes you to the **Editing mode**. The **Drop down menu** provides access to your personal data and your course data as well as the terms of use, the documentation, some general info on classEx and the logout button. You can also log out all participants currently logged into your course. 

Top bar
-------

The top bar is located in the top left corner. It is different in each submode.

Top bar - Overview mode
~~~~~~~~~~~~~~~~~~~~~~~

You can see the top bar for the **Overview mode** in the picture above. It offers folowing funcionality:

new folders
    Create new folders to organize your games

new games
    Create new games which you can then design in the editing mode

repository
    The repository which provides access to previous results from your private games or from public games conducted by you or other classEx lecturers
    
Top bar - Lecture mode
~~~~~~~~~~~~~~~~~~~~~~

The top bar of the **Lecture mode** looks like this:

.. image:: _static/MenuLecture.PNG
    :alt:  150px
    
It offers following functionality:

select games
    Select games from all public and your private games. The selected game opens up as soon as you click on it.

Login QR code
    Click on QR code to enlarge the QR code and also provide an instruction for players to enter without using the QR code

Add test players
    This button will add a test player screen in a new tab. This can be very useful to test classEx games.

Diagnosis mode
    In the diagnosis mode you can see all variables for the lecturer and the players, which makes detecting programming errors much easier.

data
    Via the dropdown menu data you can access an overview over players who are currently taking part in your game or who took part in the game of which the results are on display. The overview shows the number of participating players and which decision stage they are at. You can show this overiew on the screen via **show data**. Clicking on "back to Lecture mode" takes you back to the current game. You can also download the results via **download as excel file**. The excel files contain the decisions made in the game you just played or, if available, old results of the same game. You can also download excel files containing an overview of types, treatments & groups that existed in this game as well as players’ IDs and their log-in time.

previous results
    You can access previous results via the previous results dropdown menu. Simply choose which results from previous lectures you want to display. This way you can directly compare current outcomes with previous ones. 

Top bar - Lecture mode
~~~~~~~~~~~~~~~~~~~~~~

See `Develope your own games <https://classex-doc.readthedocs.io/en/latest/040_Develop_your_own_games.html>`_.

Terminology
===========

This chapter clarifies the usage of some terms in this documentary. 

Lecturer
    The person conducting a game is the lecturer. The lecturer starts games, starts new rounds, ends games and shows results. The lecturer controls the lecture screen that is visible for all players (typically via a projector in the lecture hall). 

Player
    Every person participating in a game is a player. All a player needs for participation is a mobile device with internet access. No download is required.

Session
    A session is a sequence of games in a lecture, meeting or presentation. Players should not shut their browser during a session, as each player receives an ID-number for a session. This allocation would be lost if player close their browsers.
    
    Tip: After the end of a session, you can use statistical tests to analyse whether there is a relationship between the different games of a session. For example, you can examine whether players with higher mathematical abilities are more risk averse. For this purpose, players' ID-numbers are stored in an Excel sheet.

Game
    Games consist of a sequence of stages. A game is typically characterised by a joint evaluation of the decisions and results at the end.
    Tip: If you want to conduct a quiz consisting of several questions with unrelated results, it is advisable to create a separate game for each question.

Stage
    Games consist of several stages. There are at least 2 stages, one for the decision input and one for the result output. Stages are ordered sequentially and are meant to be synchronization points in the game. Synchronization means that for the next stage to begin, all elements of the previous stage must have been finalized. Stages can be configured with several options. You can find more information here.

Element
    Elements are the modules of each stage. A stage has two areas in which you can add modules: player and lecturer. You can chose from text elements, input elements (numerical input, likert scales, …), program code elements and output elements (histograms, bar charts, …). These can be combined and arranged as you like.

Treatment
    Treatments allow you to treat players differently throughout a game. You can assign players to treatments and customize stages and elements for treatments.

Role
    Many games require different roles of players, e.g. producers and consumers. Stages and elements of a game can be customized according to the role of a player.

Group
    Participating players of a game can be sorted into groups, e.g. according to their role, internal ID, randomly or a combination of these.

Assignment and Matching
    Assignement and matching refers to the procedure of how players are assigned into treatments, roles and groups at the start of a game. Further, you can choose how you want to rematch players at the beginning of each round if you play more then one round.

Round and Loop
    The number of rounds a game should be played can be defined. The loop referes to the stages of a game that should be repeated in every round. The loop is defined by selecting two stages and the number of rounds. Starting in the first round the game will then jump back from the end of the later stage to the beginning of the earlier stage until the number of rounds is reached. 

Internal ID
    ClassEx creates a unique internal ID for each subject that logs in. This ID is generated randomly and does not allow any inference about the identity of the subject. Therefore, subjects are completely anonymous in classEx by default. The internal ID serves as a mean to be able to analyse the data and compare behaviour of subjects across different games if you play several in one session.

Global and subjects variables and parameters
    Global variables are variables on the game level. They have the same value for all players (e.g. current round). Subject variables are variables on the subject level. The value of a subject variable is calculated separately for every player (e.g. individual payoff). Parameters are variables that are adjustable before running a game (e.g. total number of rounds). Changing parameters does not require knowledge about how to edit games.

Global and subject program code elements
    Many games require calculations or algorithms. These are created in program code elements. The programming language used in these elements is PHP. Global program code is utilized for calculations on the game level. Subject program code is utilized for calculations on the subject level (for every player).

