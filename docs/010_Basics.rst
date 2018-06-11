.. _basic:

=====
Basic
=====

Registration and Login
======================

Lecturers are required to register in order to use classEx. Please fill in the registation form you can find `here <https://classex.de/get-login-credentials/>`_. Registered users receive a password via e-mail and hereby obtain the right of unlimited and cost-free use of classEx for teaching, further education and research (for details please see `terms of use <https://classex.de/wp-content/uploads/2018/04/TermsOfUse.pdf>`_). Students do not need to register but are involved anonymously as participants in lectures and presentations.

 .. image:: _static/Loginnew.png 
    :alt:  300px

The website https://classex.uni-passau.de displays an input screen to lecturers and students. First of all, the university needs to be selected. Next, the class or teaching unit needs to be chosen. Lecturers, students or individuals entrusted with the payoff chose their corresponding mode, enter the password and log in. Following features are available:

Students and Particpants
------------------------

Students can participate interactively in a lecture or a presentation by logging in as a “participant”. They do not need to register and remain anonymous. The lecturer choses the password and provides this to the students. More information can be found here.

Lecturers
---------

Lecturers (users) who want to actively involve their students, log in as “lecturer”. They receive their password via e-mail upon registration. Lecturers can either enter the Lecture Mode and start games and quizzes or enter the Editing Mode and adapt games or create new ones.

Administrative staff
--------------------

Individuals entrusted with the payoff can enter the Administration Mode in order to disburse the monetary payoff. This task can be delegated to a trustworthy person by the lecturer. 

Essentials
==========

This screen appears when you enter classEx. It provides you with an overview of all your games and gives you quick access to all important features of classEx.
Main classEx screens

In the top right-hand corner, you find the main navigation bar which is always displayed in every mode. This allows you to switch from one mode to another and access your personal data.

Bild1.png

The mode you are currently in, is always marked by a darker shade of grey, currently the symbol for the starting screen W.JPG. The symbol on the left Q.JPG takes you to the Lecture Mode. Clicking on F.JPG takes you to the Editing Mode. The little arrow S.JPG provides you with a drop-down menu. Here, you can access your personal data and your course data as well as the terms of use, the documentation, some general info on classEx and the logout button. You can also log out all participants currently logged into your class, for more information see Participants. 

Top bar

The top bar of the lecture mode looks like this:

TBnew.PNG

Here, you can find the following symbols:

- select game: By clicking on this, you can choose from all of your games. The selected game opens up as soon as you click on it.

- QR code symbol: Clicking on this symbol enlarges the QR code and provides an instruction for participants to enter without using the QR code.

- Testpart.JPG: Clicking on this opens a participant screen in a new tab. This can be very useful to test classEx games.

- Steto.PNG: This starts the Diagnosis mode. Here, you can see all variables for the lecturer and the players, which makes detecting programming errors much easier.

- data: drop down menu. By selecting show data, you can access a clients' table by clicking on , which shows you how many participants are logged in and what decision stage they are at. Clicking on "back to Lecture mode" takes you back to the current game. 
Showdata.JPG

- Download results: In the drop-down menu of data you can also download excel files containing the decisions made in the game you just played or, if available, old results of this same game. You can also download excel files containing an overview of roles, treatments & groups that existed in this game as well as participants’ IDs and their log-in time.

Excel.JPG


- previous results: this function lets you access results of the same game from previous lectures. This way you can directly compare current outcomes with previous ones. 

Terminology
===========

Session

A session is a sequence of experiments or games in a lecture, meeting or presentation. Participants should not shut their browser during a session, as each participant receives an ID-number for a session. This allocation would be lost if participants close their browsers.
Tip: After the end of a session, you can use statistical tests to analyse whether there is a relationship between the different games of a session. For example, you can examine whether participants with higher mathematical abilities are more risk averse. For this purpose, participants' ID-numbers are stored in an Excel sheet.
Game

Games consist of a sequence of stages. A game is typically characterised by a joint evaluation of the decisions and results at the end.
Tip: If you want to conduct a quiz consisting of several questions with unrelated results, it is advisable to create a separate game for each question.
Stages

Games consist of several stages. There are at least 2 stages, one for the decision input and one for the result output. Stages are ordered sequentially and are meant to be synchronization points in the game. Synchronization means that for the next stage to begin, all elements of the previous stage must have been finalized.

Stages can be configured with several options. You can find more information here.
Assignment and Matching

You can define the basic settings of your game by choosing to assign participants to roles, treatments, groups etc. Further, you can choose how you want to rematch participants if you play several rounds.
Elements

Elements are the modules of each stage. A stage has two areas in which you can add modules: participants and lecturer.

You can chose from text elements, input elements (numerical input, likert scales, …), programme elements and output elements (histograms, bar charts, …). These can be combined and arranged as you like.

More information on Elements. 

Game and Session
----------------

Stage and Element
-----------------

Player and Lecturer
-------------------

Round and Loop
--------------

Player, Type and Group Internal & external ID
---------------------------------------------

Identification of subjects in the system
Internal ID

By default, subjects are completely anonymous in classEx. classEx creates a unique internal ID for each subject that logs in. This ID is generated randomly and does not allow any inference about the identity of the subject. It serves as a mean to be able to analyse the data and compare behaviour of subjects across different games if you play several in one session.
External ID

Should it be required, you also have several possibilities to identify subjects in the system.

Ticket: You can provide participants with a personalised ticket to log-in to classEx. This way you can ensure that participants only take part on one device and also track the actions of specific participants. You simply need to add &tic= to the URL. The ticket is saved to the player data and can be retrieved as $tic; in the game.

Ask for data during the game: At a certain stage, or after the end of the game, you can ask participants to enter their personal data or an ID you provide them with.

During login: You can change the settings so that participants are asked for certain data before they log-in. For this, go to "course data" and click on additional settings. You can then enter what you would like participants to enter before logging in.

Here is an example:

Data1.PNG

And this is what it looks like for participants before login:

Data2.PNG 


Global and subjects variables and parameters
--------------------------------------------

Interaction types (sequential interaction, simulatenous,…)
----------------------------------------------------------

Ready-made games
================
This page provides an overview of the possible applications of classEx on the basis of diverse types of games. These are only some example. Many more games can be found in the repository in classEx.
Contents

    1 Game Description
    2 Alphabetical List of Games
    3 Standard Games
    4 Categorization of Game Structure
    5 Individual Choice
        5.1 Single Choice
            5.1.1 Single Choice with Random Events
            5.1.2 Single Choice with Treatments
        5.2 Multiple Choice
        5.3 Numeric Data
            5.3.1 With Treatments
    6 Strategic Interaction
        6.1 Simultaneous | 1 Role
            6.1.1 Discrete
            6.1.2 Numeric
        6.2 Simultaneous | 2 Roles
            6.2.1 Discrete
            6.2.2 Numeric
        6.3 Sequential | 2 Roles
            6.3.1 Discrete
            6.3.2 Numeric
        6.4 Continuous | 2 Roles

Game Description

In order to store and search for games the following information provides a definition of a game.
Name 	A short name which describes the game
Game Structure 	Individual vs. Strategic Choice (sim, seq or cont)
Roles 	Number of Roles
Alphabetical List of Games

Find an alphabetical listing of all games featured in this Wiki here.
Standard Games

classEx provides users with a set of ready-made games that come with a classEx account. You can find these in the Overview on the Starting Screen. This provides examples of different applications of classEx and also gives you ready-made games for some of the standard experiments such as the Public Goods Game or the Trust Game.
Categorization of Game Structure

classEx builds on a simple categorization of games. The categorization builds on the structure of the games. It first distinguished between individual and strategic choice. The latter then can be classified into simultaneous, sequential or continous games.
Individual Choice 	Strategic Choice
	Simulataneous 	Sequential 	Continuous
Individual Choice

Individual Choice means decisions of individuals which are made alone. No strategic interaction with other participants takes place. In the following, you can see a few examples of Individual Choice games that can be implemented with classEx.
Single Choice

The easiest type of questions are Quiz Questions as they can be also in found in standard Audience Response System. Participants choose among a set of options.
Single Choice with Random Events

Simple questions combined with a random event are a different type of application for Individual Choice games. This way, participants can be animated to think about decisions with unsure outcomes and payoffs. Lecturers can use this to show relevant applications in, for example, statistics, stochastics, finance or the insurance industry. For instance, participants can place a bet on a coin toss. You can also test to which extent participants are willing to take a risk. In the following, you can find a few examples of how random events can be implemented in classEx:

Ellsberg Paradoxon

Lottery and Risk Preference

Search Costs
Single Choice with Treatments

Treatments are a great possibility to expand Individual Choice questions. With these, two (or more) variations of the same game can be played. Participants are divided into two groups of the same size and, for example, see different scenarios for the same game. Each group then plays a different treatment and differences between the two treatments allow for conclusions regarding the impact of different scenarios. To implement this, you need to choose the option “Treatment” in list “Treatments, roles & groups” and specify the number of treatments. It is possible to display different information, so-called private information, on the mobile devices of the two groups. A well-known example for the use of treatments is the “Asian disease” presented by Tversky and Kahnemann (Science 1981) which exemplifies a cognitive bias. Similarly, framing and priming effects can be determined with a game. In the following, you can find a few examples of how treatments can be used in classEx:

Ethical Dilemma

Nudge

Wage Increase
Multiple Choice

Opinion polls differ from quiz questions in the sense that you cannot classify one answer as correct. Further, it may be possible to choose more than one answer (Multiple Choice).

Effects of inflation
Numeric Data

Decisions of participants can also require an input of numbers. For this, simply choose “Numeric input field” as the type of input field in the Editing Mode. A game that uses this form of input is shown below:

Estimation Task.
With Treatments

You can also implement several treatments in games with numeric input. For example:

Distribution of Income
Strategic Interaction

With classEx, strategic interaction in the lecture can be modelled, too. It offers games which can be conducted simultaneously, sequentially or continously (not yet implemented). Furthermore, the type of the game is determined by the number of roles. Participants can be assigned to different roles Role1.PNG Role2.PNG. Every role is related to a seperate task and interaction.
Simultaneous | 1 Role

In a simple variation with strategic interaction, all participants have the same role and only interact with each other in one big group. Contrary to individual choice games, the result is influenced by the decisions of all other participants in the lecture.
Discrete

Workplaces in the Library^

Schelling Salience (Faces Beauty Contest)
Numeric

Common Value Auction

Private Value English Auction

Beauty Contest

Tragedy of the Commons

Public Goods Game, Common-Pool Resource Game or Minimum-Effort Game
Simultaneous | 2 Roles
Discrete

This sort of game entails standard Matrix Games:

Battle of the Sexes

Chicken Game

Hawk-Dove Game

Stag Hunt

Prisonners Dilemma

Coordination Game

All of these might be carried out with multiple treatments.
Numeric

Dictator Game

Ultimatum Game with MAO°
Sequential | 2 Roles

Sequential games can be modelled with two or more stages.
Discrete

Principal-Agent

Centipede Game


Numeric

Labor Contract

Trust Game

Ultimatum Game

Alternating Offer Bargaining


Continuous | 2 Roles

Continuous games are not yet implemented in classEx. This will be done in the near future.

Unstructured Bargaining

Dutch Auction

Double Auction 
















