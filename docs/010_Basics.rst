.. _basic:

======
Basics
======

Requirements
============

classEx is an online tool which runs centralized at the servers of the University of Passau. Therefore, no installation of software or download of applications is necessary. Running games and developing games is done in a standard internet browser.

Lecturers only need an up-to-date browser and an internet connection. We suggest to use Firefox. Make sure that javascript is enabled and cookies are allowed (normally this is a default setting in many browsers). **Do not use Internet Explorer for using classEx because classEx does not run with it.**

For using classEx you only need to register in order to get login credentials.

Registration
============

In order to get login credentials, please fill in the registation form at https://classex.de/get-login-credentials.

For registration you have to provide your name, an email address and information about your institution. In addition, you have to confirm that you accept the `terms of use`_ and the data privacy policy. **Please try to provide an institutional email address so that we can verify your affiliation.** Registered users receive an email with login credentials. Login credentials are normally sent within 1-2 days. If you do not receive credentials after 2 days, please contact us at `classEx@uni-passau.de <mailto:classEx@uni-passau.de>`_.

Each user has an account (called course in classEx) which is linked to their institution. With the login credentials you obtain the right to use classEx for teaching, education, research and other purposes (for details please see `terms of use`_).

Students do not need to register but can access classEx with the course password provided to the lecturer with the login credentials.

Login
=========

.. image:: _static/basics/login.PNG
    :alt:  200px

The website https://classex.uni-passau.de shows the login for lecturers and students.

Institution
    Select the institution you named during your registration, typically your university.

Course
    Select your course or another course you have access to.

User types
    - Participants: Students can participate interactively in a lecture or a presentation by logging in as a participant. They do not need to register and remain anonymous. They select the university and the course from the lecturer's registration. The lecturer provides the course password. Participation after logging in is self-explanatory and does not require any previous knowledge.

    - Lecturer: Registered lecturers who have received a password can login as experimenter/lecturer. As lecturer you can organize your account, start ready-made games and quizzes, adapt them to your liking or create new ones. This documentation mainly explains the possibilities and options classEx offers for lecturers.

    - Administration: Individuals entrusted with the payoff can enter the administration mode in order to disburse the monetary payoff. This task can be delegated to a trustworthy person by the lecturer. You can find further instructions `here <https://classex-doc.readthedocs.io/en/latest/020_Run_a_ready-made_game.html#payoffs-and-administration-mode>`_.

Password
    A registered lecturer has received a password upon registration. Participants are provided with their password by the lecturer. The password can also be used for the administration user type.

Essentials for lecturers
=========================

.. only:: html

    <div style="text-align: center; margin-bottom: 2em;">
    <iframe width="100%" height="350" src="https://www.youtube.com/embed/Zm0DpUzhOGg" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>

.. raw:: latex

    You can find a short video on how to use classEx on https://www.youtube.com/embed/Zm0DpUzhOGg

Entering classEx as a lecturer offers three modes: overview mode, lecture mode and editing mode. After login, the screen shows the overview mode. Here you can organize your games and access all important features of classEx. In the lecture mode you can run games, in the Editing mode you can develop your own games.

.. image:: _static/Overview.PNG
    :alt:  300px

Navigation bar
--------------

In the top right-hand corner, you find the main navigation bar which is always displayed in every mode. This allows you to switch from one mode to another and access your personal data.
    
The currently active mode is marked by a darker shade around its symbol, here the **overview mode**. The left symbol takes you to the **lecture mode**. The right symbol takes you to the **editing mode**. The **Drop down menu** provides access to your personal data and your course data as well as the `terms of use`_, the documentation, some general info on classEx and the logout button. You can also log out all participants currently logged into your course.

Top bar
-------

The top bar is located in the top left corner. It is different in each mode.

Top bar - overview mode
~~~~~~~~~~~~~~~~~~~~~~~

You can see the top bar for the **overview mode** in the picture above. It offers folowing funcionality:

new folders
    Create new folders to organize your games

new games
    Create new games which you can then design in the editing mode

repository
    The repository which provides access to previous results from your private games or from public games conducted by you or other classEx lecturers
    
Top bar - lecture mode
~~~~~~~~~~~~~~~~~~~~~~

The top bar of the **lecture mode** looks like this:

.. image:: _static/MenuLecture.PNG
    :alt:  150px
    
It offers following functionality:

select games
    Select games from all public and your private games. The selected game opens up as soon as you click on it.

Login QR code
    Click on QR code to enlarge the QR code and also provide an instruction for participants to enter without using the QR code

Add test participants
    This button will add a test participant screen in a new tab. This can be very useful to test classEx games.

Diagnosis mode
    In the diagnosis mode you can see all variables for the lecturer and the participants, which makes detecting programming errors much easier.

data
    Via the dropdown menu data you can access an overview over participants who are currently taking part in your game or who took part in the game of which the results are on display. The overview shows the number of participating participants and which decision stage they are at. You can show this overiew on the screen via **show data**. Clicking on "back to lecture mode" takes you back to the current game. You can also download the results via **download as excel file**. The excel files contain the decisions made in the game you just played or, if available, old results of the same game. You can also download excel files containing an overview of types, treatments & groups that existed in this game as well as participants’ IDs and their log-in time.

previous results
    You can access previous results via the previous results dropdown menu. Simply choose which results from previous lectures you want to display. This way you can directly compare current outcomes with previous ones. 

Top bar - lecture mode
~~~~~~~~~~~~~~~~~~~~~~

See `Develope your own games <https://classex-doc.readthedocs.io/en/latest/040_Develop_your_own_games.html>`_.

Terminology
===========

This chapter clarifies the usage of some terms in this documentary. It can used to look up terminology.

Lecturer
    The person conducting a game is the lecturer. The lecturer starts games, starts new rounds, ends games and shows results. The lecturer controls the lecture screen that is visible for all participants (typically via a projector in the lecture hall).

Participant
    Participants participate in games. All a participant needs for participation is a mobile device with internet access. No download is required. Sometimes participants are also called players.

Session
    A session is a sequence of games in a lecture, meeting or presentation. participants should not shut their browser during a session.
    
    Hint: After the end of a session, you can use statistical tests to analyse whether there is a relationship between the different games of a session. For example, you can examine whether participants with higher mathematical abilities are more risk averse. For this purpose, participants' ID-numbers are stored in an Excel sheet.

Game
    Games consist of a sequence of stages. A game is typically characterised by a joint evaluation of the decisions and results at the end.
    Hint: If you want to conduct a quiz consisting of several questions with unrelated results, it is advisable to create a separate game for each question.

Stage
    Games consist of several stages. There are at least 2 stages, one for the decision input and one for the result output. Stages are ordered sequentially and are meant to be synchronization points in the game. Synchronization means that for the next stage to begin, all elements of the previous stage must have been finalized. Stages can be configured with several options. You can find more information here.

Element
    Elements are the modules of each stage. A stage has two areas in which you can add modules: participant and lecturer. You can chose from text elements, input elements (numerical input, likert scales, …), program code elements and output elements (histograms, bar charts, …). These can be combined and arranged as you like.

Treatment
    Treatments allow you to treat participants differently throughout a game. You can assign participants to treatments and customize stages and elements for treatments.

Role
    Many games require different roles of participants, e.g. producers and consumers. Stages and elements of a game can be customized according to the role of a participant.

Group
    Participating participants of a game can be sorted into groups, e.g. according to their role, internal ID, randomly or a combination of these.

Assignment and Matching
    Assignment and matching refers to the procedure of how participants are assigned into treatments, roles and groups at the start of a game. Further, you can choose how you want to rematch participants at the beginning of each round if you play more then one round.

Round and Loop
    The number of rounds a game should be played can be defined. The loop refers to the stages of a game that should be repeated in every round. The loop is defined by selecting a starting stage and ending stage and the number of rounds.

Internal ID
    ClassEx creates a unique internal ID for each subject that logs in. This ID is generated randomly and does not allow any inference about the identity of the subject. Therefore, subjects are completely anonymous in classEx by default. The internal ID serves as a mean to be able to analyse the data and compare behaviour of subjects across different games if you play several in one session.

External ID
    On login, participants can be asked to provide an external ID (e.g. their matriculation number). The external ID can also be provided with the link for automatic login. Please make sure that you elicit external IDs in accordance with data privacy regulations as the lecturer is responsible for this during data collection (see `terms of use`_).


.. _terms of use: https://classEx.de/TermsOfUse.pdf


Subject ID
    Subject IDs are used only within a game. Each participant gets an ID from 1 to the total number of participants. The fist participants gets the Subject ID 1, the second participant the Subject ID 2, and so forth.


Global and subjects variables
    Global variables are variables on the game level. They have the same value for all participants (e.g. an exchange rate). Subjects variables are variables on the subject level. The value of a subject variable is calculated separately for every participant (e.g. individual payoff).

Parameters
    Parameters are global variables that are adjustable before running a game (e.g. the endowment). Parameters can be changed directly in the lecture mode. They have the same value for all participants.

Global and subject program code elements
    Many games require calculations or algorithms. These are created in program code elements. The programming language used in these elements is PHP. Global program code is utilized for calculations on the game level. Subject program code is utilized for calculations on the subject level (for every participant).

