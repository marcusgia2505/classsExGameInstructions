.. _basic:

======
Basics
======

Registration
============

Lecturers who want to actively involve their students are required to register in order to use classEx. Please fill in the registation form you can find `here <https://classex.de/get-login-credentials/>`_. Registered users receive a password via e-mail and hereby obtain the right of unlimited and cost-free use of classEx for teaching, further education and research (for details please see `terms of use <https://classex.de/wp-content/uploads/2018/04/TermsOfUse.pdf>`_). Students do not need to register but are involved anonymously in lectures and presentations.

Login
=====

.. image:: _static/Login.PNG
    :alt:  300px


The website https://classex.uni-passau.de displays an input screen to lecturers and students. First of all, the university needs to be selected. Next, the class or teaching unit needs to be chosen. Lecturers (experimenter/lecturer), students (player) or individuals entrusted with the payoff (administration mode) chose their corresponding user mode, enter the password and log in. Following features are available:

User modes
----------

- Player: Students can participate interactively in a lecture or a presentation by logging in as a “player”. They do not need to register and remain anonymous. They select the university and the course from the lecturer's registration. The lecturer provides the password he has chosen for players in his course. Participation after logging in is self-explanatory and does not require any previous knowledge.

- Lecturer: Registered lecturers who have received a password can login as "lecturer". As lecturer you can organize your account, start ready-made games and quizzes, adapt them to your liking or create new ones. This documentation mainly explains the possibilities and options classEx offers for lecturers.

- Administration mode: Individuals entrusted with the payoff can enter the administration mode in order to disburse the monetary payoff. This task can be delegated to a trustworthy person by the lecturer. You can find further instructions `here <https://classex-doc.readthedocs.io/en/latest/020_Run_a_ready-made_game.html#payoffs-and-administration-mode>`_. 

Essentials
==========

This screen appears when you enter classEx. It provides you with an overview of all your games and gives you quick access to all important features of classEx.

.. image:: _static/Startscreen.PNG
    :alt:  300px

In the top right-hand corner, you find the main navigation bar which is always displayed in every mode. This allows you to switch from one mode to another and access your personal data.

.. image:: _static/Bild1.png
    :alt:  100px
    
The mode you are currently in, is always marked by a darker shade of grey, currently the symbol for the starting screen W.JPG. The symbol on the left Q.JPG takes you to the Lecture Mode. Clicking on F.JPG takes you to the Editing Mode. The little arrow S.JPG provides you with a drop-down menu. Here, you can access your personal data and your course data as well as the terms of use, the documentation, some general info on classEx and the logout button. You can also log out all participants currently logged into your class, for more information see Participants. 

Top bar

The top bar of the lecture mode looks like this:

.. image:: _static/TBnew.PNG
    :alt:  300px
    
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

Quiz questions
Quiz questions, such as the one above, are the easiest type of application in classEx. The lecturer can set any number of options. These can be labelled randomly, e.g. as Option 1, Option 2, etc., but can also include short answers. Quiz questions are mostly built up in the way that only one answer can be selected (Single Choice) and one or more of them can be classified as correct. For presentation purposes the lecturer has the opportunity to highlight the correct answer in colour. This occurs by marking the relevant option in the [[Editing Mode]]. 
<div class="quote">
Tip: Since most of the mobile devices have small screen sizes, not more than 4-5 briefly described options should be set.</div>

Single Choice with Random Events

Simple questions combined with a random event are a different type of application for Individual Choice games. This way, participants can be animated to think about decisions with unsure outcomes and payoffs. Lecturers can use this to show relevant applications in, for example, statistics, stochastics, finance or the insurance industry. For instance, participants can place a bet on a coin toss. You can also test to which extent participants are willing to take a risk. In the following, you can find a few examples of how random events can be implemented in classEx:

Ellsberg Paradoxon

[[File: Ellsberg.PNG | right]]

One possible application for games with random events is the so-called Ellsberg paradox. You can find games concerning this paradox under the titles “Ambiguity 1” and “Ambiguity 2”. 

In these games, an urn contains 90 balls, 30 of which are red and 60 of which are either black or yellow. The proportion of black and yellow balls is unknown. Now, one ball is drawn from the urn. Participants can bet on a red or a black ball. If a yellow ball is drawn, participants win nothing. Results show that participants rather bet on red balls, hence, they try to avoid the uncertainty connected with betting on a black ball. 


== Special feature: Random Draw ==

[[File: Ellsberg_code.PNG | right]]
The special thing about this game is that you can actually implement random draws. Participants, therefore, can be informed about whether they would have won or not. For this, you need to implement a random draw in the second stage in classEx. You simply write a small program with PHP-function rand(); in order to draw a ball. The outcome is displayed in a text field. You can find a detailed description of programmes in [[Elements]].

Lottery and Risk Preference

A test to determine subjects‘ risk preferences was presented by Holt and Laury (American Economic Review 2002). The following experiment shows how this works. 10 situations are presented to the participants, who then choose between a low-risk option A and a high-risk option B for each situation.

                               '''Option A'''                                       '''Option B'''
 '''Situation 1'''    €2 with p = 1/10 and €1.60 with p = 9/10	   €3,85 with p = 1/10 und €0.1 with p = 9/10 
 '''Situation 2'''    €2 with p = 2/10 und €1.60 with p = 8/10	   €3,85 with p = 2/10 und €0.1 with p = 8/10 
 '''Situation 3'''    €2 with p = 3/10 und €1.60 with p = 7/10	   €3,85 with p = 3/10 und €0.1 with p = 7/10
 '''Situation 4'''    €2 with p = 4/10 and €1.60 with p = 6/10    €3,85 with p = 4/10 and €0.1 with p = 6/10
 '''Situation 5'''    €2 with p = 5/10 und €1.60 with p = 5/10	   €3,85 with p = 5/10 und €0.1 with p = 5/10 
 '''Situation 6'''    €2 with p = 6/10 und €1.60 with p = 4/10	   €3,85 with p = 6/10 und €0.1 with p = 4/10 
 '''Situation 7'''    €2 with p = 7/10 und €1.60 with p = 3/10	   €3,85 with p = 7/10 und €0.1 with p = 3/10 
 '''Situation 8'''    €2 with p = 8/10 und €1.60 with p = 2/10	   €3,85 with p = 8/10 und €0.1 with p = 2/10
 '''Situation 9'''    €2 with p = 9/10 und €1.60 with p = 1/10	   €3,85 with p = 9/10 und €0.1 with p = 1/10 
 '''Situation 10'''   €2 with p = 10/10 und €1.60 with p = 0/10   €3,85 with p = 10/10 und €0.1 with p = 0/10           
               
Lecturers should explain that a few randomly drawn participants will receive a payoff. One of the ten situations will be drawn for the randomly chosen participants and another random draw will determine whether the first or second value will be paid out.
You need to create a separate input (Single Choice input options) for each of the ten situations, which means that participants will make ten decisions altogether. 

<div class="error">This game is not yet implemented in classEx.</div>

Search Costs

Decisions and random draws can also be implemented over several rounds. As an example, classEx provides a game in which the advantages and disadvantages of a continued search are demonstrated. While searching for a suitable craftsman, participants need to invite several offers that are determined randomly and, therefore, cause subjects to weigh up the costs of searching and the improvement of offers through a continued search.

The costs of searching are 1.20€ per offer. Participants can invite up to five offers with the value of the craftsman’s service varying between 0 and 20 euros. The participants’ payoff is determined by the craftsman with the highest value among the invited offers, minus the costs of searching.
This game was played during the lecture Economics of Institutions in the summer semester 2012. A video (in German) can be found [http://www.wiwi.uni-passau.de/wirtschaftstheorie/classex-interaktive-hoersaalexperimente/anwendungsbeispiele/  here].

Single Choice with Treatments

Treatments are a great possibility to expand Individual Choice questions. With these, two (or more) variations of the same game can be played. Participants are divided into two groups of the same size and, for example, see different scenarios for the same game. Each group then plays a different treatment and differences between the two treatments allow for conclusions regarding the impact of different scenarios. To implement this, you need to choose the option “Treatment” in list “Treatments, roles & groups” and specify the number of treatments. It is possible to display different information, so-called private information, on the mobile devices of the two groups. A well-known example for the use of treatments is the “Asian disease” presented by Tversky and Kahnemann (Science 1981) which exemplifies a cognitive bias. Similarly, framing and priming effects can be determined with a game. In the following, you can find a few examples of how treatments can be used in classEx:

Ethical Dilemma

[[File: Dilemma.PNG | right]]

A different application of treatments can be found in experimental ethics. Here, a growing strand of literature is dealing with the diffusion of responsibility. Participants need to weigh up self-serving options, which promise money or convenience, or altruistic options that benefit other people or fulfil social norms or laws. Results show that the self-serving option is chosen more often if participants can shirk their responsibility for other goals. classEx provides a game that covers this topic called “Ethical Dilemma”. In this game, a scenario is described (see figure). Two different treatments are implemented. Half of the participants get the description marked with an orange color. The other half get the description marked with a blue color. The treatment effect can be directly observed.


Nudge


[[File: Nudge.PNG | right]]

A different example concerns the influence of a default on human behaviour. This is discussed thoroughly in Thaler and Sunstein’s book Nudge (2009). A nudge is a small push that directs participants to one decision or another. [[wikipedia:Nudge|Nudges]] can often be found when filling in surveys or questionnaires if one option is marked as default. Marking another option then requires an explicit decision. This can be illustrated by an experiment in which participants are asked whether or not they would like to participate in a company retirement plan. Two groups are asked to decide for or against a retirement plan, however, in the first group, the pro-option is marked as default and the other group has the contra-option marked. Results show that this treatment strongly influences participants‘ decisions. Those who have the contra-option set as default opt against the insurance scheme more often than those with the other option marked. This can be implemented in the [[Editing Mode]] by indicating the relevant variable in the “Default” field.


Wage Increase

[[File: Wageincrease.PNG |right]]

The number of treatments is not limited to two. For example, different wage scenarios and their influence on participants’ motivation to work can be analysed. In their [http://press.princeton.edu/titles/8967.html| book Animal Spirits] (2009), Akerlof and Shiller suggest that people’s motivation to work is guided by nominal wages and that inflation rates are not considered sufficiently. In classEx, you can find a game called “Wage Increase” that covers this topic. Three different treatments are implemented in this game. Participants are asked how their motivation to work changes in reaction to different wage increases and inflation rates. This game enables an analysis of whether participants react to nominal or real wage increases.

Multiple Choice

Opinion polls differ from quiz questions in the sense that you cannot classify one answer as correct. Further, it may be possible to choose more than one answer (Multiple Choice).

Effects of inflation
[[File: Mc.PNG | right]]

An example for an opinion poll with multiple choice answers is the question of the effects on inflation, where more than one answer may be correct.


You can implement such an opinion poll in classEx, by selecting “Check boxes (Multiple Choice)” in the [[Editing Mode]]. None of the options should be marked as correct. Furthermore, you need to select “Multiple Choice” for the evaluation of results.

<div class="quote">Tip: You can easily change the order of answer options by drag & drop. Simply click onto the number of the option you would like to change and drag it to the new position.</div>

Numeric Data

Decisions of participants can also require an input of numbers. For this, simply choose “Numeric input field” as the type of input field in the Editing Mode. A game that uses this form of input is shown below:

Estimation Task
[[File: numberindic.PNG|right]]

Decisions of participants can also require an input of numbers. For this, simply choose “Numeric input field” as the type of input field in the [[Editing Mode]]. Participants are asked to estimate the number of lines of a famous German poem. The right answer is marked by the red line.

With Treatments

You can also implement several treatments in games with numeric input. For example:

Distribution of Income
The distribution of income into consumption and savings is another example for the implementation of treatments with numerical input. Here, participants specify which percentage of a payment they want to use for certain purposes. This allows an analysis of the well-known macroeconomic theory of Ricardian Equivalence, i.e. the question whether households take future tax payments into account while determining their current consumption behaviour. In classEx, you find such a game called '''“Consumption and Government Spending”'''. In this game, participants are told that each citizen receives a large amount of money from the government. They then have to decide how much of this money they want to spend for non-durable consumer goods, how much they want to spend for durable consumer goods and how much they want to save. Two treatments are implemented which differ in regard to the way in which the government finances these payments. In the one treatment, the government has found new natural resources which finance the payments. In the second treatment, the government finances the payments via credits, i.e. the emission of new government bonds (which would then lead to higher future tax rates). Results show that the treatment only has a small influence on the level of savings. Therefore, evidence for the theory of Ricardian Equivalence is rather small.

Strategic Interaction

With classEx, strategic interaction in the lecture can be modelled, too. It offers games which can be conducted simultaneously, sequentially or continously (not yet implemented). Furthermore, the type of the game is determined by the number of roles. Participants can be assigned to different roles Role1.PNG Role2.PNG. Every role is related to a seperate task and interaction.
Simultaneous | 1 Role

In a simple variation with strategic interaction, all participants have the same role and only interact with each other in one big group. Contrary to individual choice games, the result is influenced by the decisions of all other participants in the lecture.

Discrete

Workplaces in the Library^

Schelling Salience (Faces Beauty Contest)
The Faces Beauty Contest goes back to [http://de.wikipedia.org/wiki/John_Maynard_Keynes John Maynard Keynes] (1936). Here, the participants choose the two most beautiful faces. Precisely, the instructions go as follows: 

<blockquote style="background-color: lightgrey; border: solid thin grey;">"''Please choose the two prettiest faces among the following eight faces. The two faces which are chosen most often gain the title "man of the year". Of those participants who opted for that pair of faces, one participant is drawn randomly and will earn 20 €.''"</blockquote>

[[File:SchellingSalience.jpg | right]]
The eight faces are shown in the figure in the right corner in which you can find the faces of the two lecturers themselves. For the participants, these stand out prominently. This prominence is called [[Schelling Salience]]. With this, participants are able to agree on the selection of the two lecturers as a pair. Everybody who does that maintains his / her opportunity to win. As in the case of Keynes, people are not selected with regard to their beauty, but dependent on the achievable profit. For Keynes, this was an example for the fact that investors don’t buy the best asset but those which they can sell to others most successfully.


Numeric

Common Value Auction

[[File:Zinstender.jpg | right ]]
For all participants, a purchased product has the same value ('''Common Value'''). Still, participants differ in their bidding behaviour as well as in their expectations with regard to other participants. An example for this is the auction of '''Central Bank Credits''' with a loan period of one year. Every participant plays the role of a bank. Every bank submits a tender for credits of the Central Bank to the maximum amount of 5000€. Doing this, any interest rate with two decimal places can be chosen. Every bank can split up their bid into up to three interest rates. For instance, Bank A bids 1000€ for 2.4%, 2000€ for 2.5% and 2000€ for 2.7%. The bank lends the obtained resources to others at a rate of 3%. That is why 3% is the maximum interest rate of the bids.

The lecturer can set the total volume of Central Bank Credits, which are put up for auction, in advance. Consequently, the equilibrium interest rate is determined at the value at which the demanded volume of the participants just equals the provided volume of the Central Bank, e.g. 2.2% as depicted in the figure. Participants win a tender for those bids which at least equal this equilibrium interest rate. Bank A would receive the full amount of 5000€, since every bid is higher than 2.2%. If the equilibrium interest rate was higher, e.g. at 2.5%, Bank A would receive 2000€ for 2.7% for sure. If the volume of the bids at the equilibrium interest rate is higher than the allocated Central Bank Credits, it is down-scaled. Here, the allotment interest rate may be 25%. Bank A would now be allocated 500€ (2000€*0.25) at an interest rate of 2.5%.

This procedure is equivalent to an American auction. The lecturer determines in advance, which rate of interest the participant has to pay, either the interest rate offered for each individual bid ('''American auction'''; multiple rate auction) or the equilibrium interest rate ('''[[Dutch Auction]]'''; single rate auction). One participant is chosen randomly for who the payoff is carried out for the selected amount by calculating the interest rate difference from 3% each and multiplying it with the allocation amount. Thus, on the screen of the lecturer, the corresponding demand curve is displayed.

Private Value English Auction

Beauty Contest


[[File:BeautyContest.jpg | right]]
A frequently used game is the so called [[Beauty Contest]]. All participants choose a natural number between 0 and 200. From all numbers picked, the mean is calculated. The participant who comes closest to this mean wins and gets a payoff. A tie is solved by drawing a lot. 

In this game, no Nash Equilibrium exists, because every number presents a possible solution. This game demonstrates the dependence of human behaviour on historical experiences. The figure to the right shows a second round of a Beauty Contest, after reporting an average of 107 in the first round. Obviously, a convergence to the previous number occurred, although it does not describe any equilibrium.

Often, variants of the Beauty Contest are implemented, in which the person who comes closest to the mean does not win. Rather, the average is first multiplied by a number p. If, for example, the number p=2/3 is selected, the participants should choose a number which is lower than the average of the other participants' chosen numbers. These results allow for a conclusion to be drawn on how accurately the participants think through strategic interaction, how expectations with regard to the behaviour of others are formed and whether they commit an error themselves.


Tragedy of the Commons

[[File:Commons.PNG | right]]

The Tragedy of the Commons describes how a common good can be used excessively. This becomes clear in the following description of the game: All participants in the lecture want to send their cows to graze the meadow in the mountains. At the beginning, the quality (Q) of the meadow is 1 (100%). Depending on the average punching of the cattle, a, the quality of the following period is defined as:[[File:AllmendeFormula.jpg | 150px]]

You play a game with a duration of 5 years (rounds). For your payoff, the quantity of the punching of the cattle is multiplied by the quality and summed up over all five rounds. The amount will be disbursed in euros and assigned to a player randomly determined by a lottery ticket. In the figure below, the initial situation is shown. Over five rounds, the tragedy can be observed: A constant reduction of quality of the alpine meadow, causing damage to the group.

Public Goods Game, Common-Pool Resource Game or Minimum-Effort Game

[[File:PublicGoodsGame.jpg | right]]
A Public Goods Game is mostly conducted in smaller groups, thus, the participants of the lecture do not all play in one big group. In the Public Goods Game depicted below, five persons interact in a group and decide individually how much of their initial endowment they want to pay into a public account. The game is played over 10 rounds and the groups are identical over all these rounds (partner protocol). For one deposited Euro, every participant receives 0.50€, so that, individually, a payment is not worthwhile. But a participant hopes for high payments of other participant since returns accrue from this. The figure shows a typical result: The willingness to pay decreases over time.

Simultaneous | 2 Roles
Discrete

This sort of game entails standard Matrix Games:

Battle of the Sexes
Strategic interaction games often entail two players who interact and play in different roles. In the easiest case, each player can choose between to options, so that the payoff can be displayed in a 2x2 matrix. This form of display is supported by classEx.

The battle of the sexes game is an example for a strategic interaction game with two roles. Two players would like to see each other again but each prefer a different place. They must decide simultaneously which option they choose. Player 1 has a higher payoff for option A, whereas player 2 to has a higher payoff for option B. However, if players do not coordinate on the same choice, both receive a payoff of zero because. Depending on the setting, one of the two options can emerge as point of coordination.

Chicken Game

Hawk-Dove Game

Stag Hunt
[[File:staghunt.PNG | right]]

Standard matrix games can be implemented in classEx. Like the famous [[wikipedia:Stag hunt|Stag-Hunt Game]]. Players are matched with a partner in the lecture room and have to decide. After all made their decisions, the game is closed and the result is displayed.

Prisonners Dilemma
[[File:Pd.PNG| right]]

Standard matrix games can be implemented in classEx. Like the famous [[wikipedia:Prisoner's dilemma|Prisoner's dilemma]]. Players are matched with a partner in the lecture room and have to decide. After all made their decisions, the game is closed and the result is displayed.

Coordination Game

[[File:Investment.PNG | right]]

Treatments can also be implemented for games with two roles in order to study, for instance, effects of differences in the environment of the decision or different incentives. The macroeconomic book of Akerlof and Shiller ([http://press.princeton.edu/titles/8967.html | Animal Spirits 2009]) presents the idea that investments are only made if other investors simultaneously decide to do so, too. This relationship is investigated in the game “Coordinated Investment”, by providing private information to participants of the otherwise identical [[wikipedia:Coordination game|Coordination Game]]. In one treatment, this information reads that the investment is made in Germany. In another treatment, the country of destination of the investment is Greece, which was suffering an [[wikipedia::European debt crisis|economic crisis]] at the time of conducting the experiment.

All of these might be carried out with multiple treatments.
Numeric

Dictator Game
A dictator game can be easily implemented in classEx. Here, you will require a numeric input field. Player 1 receives an endowment and can then decide how much of this endowment to transfer to player 2. Player 2 is passive in this game and can make no decision.

Ultimatum Game with MAO°
In the ultimatiom game in the strategy method, both players make a decision simultaneously.
Player 1 takes the role of the proposer and is endowed with a certain amount. He may then transfer all, some or none of this endowment to player 2.
In the ultimatum game, player 2 then decides whether to accept or reject the proposed division of the pie. If player 2 rejects, both players receive a payoff of zero. When the ultimatum game is implemented in the strategy method, player 2 is presented with all possible divisions. She then decides which offers she would reject and which she would accept. At this point, player 2 is not yet informed about the actual decision of player 1.
This strategy method is usually implemented to extract players' minimum acceptable offer (MAO).

Sequential | 2 Roles

Sequential games can be modelled with two or more stages.
Discrete

Principal-Agent

A sequential game consists of at least three stages. In the first stage, player 1 http://classex.uni-passau.de/classex3/pic/role1.png makes a decision. In the second stage, player 2 http://classex.uni-passau.de/classex3/pic/role2.png makes a decision. In the third stage, the results are displayed.

The pricipal agent game is an example for sequential games that can be implemented with classEx:

A principal agent situation can be found in many economic interactions like, for example, between an owner and a manager or broker. In classEx, you will find an easy implementation for a labour contract in which an employer (principal) chooses the type of contract and the employee (agent) then chooses his level of effort as a reaction to the contract. This set-up presents a simplification of Brown, Falk and Fehr's (2002) gift-giving in the labor market, implemented without repitition.
The level of effort chosen by the agent determines the revenue of the principal. The principal can choose between three different payment systems:
a fixed wage without a share of the revenue, a share of the revenue without a fixed wage and a mixture of the two, labelled Bonus. The systems in which the agent receives a share of the revenue involve organisational costs. Therefore, following table results:

{| class="wikitable" style="border:solid 2px #999999;font-size:96%;"
|- class="hintergrundfarbe8"
! style="width:20%;font-size:103%;" | 
! style="width:20%;font-size:103%;" | Fixed wage
! style="width:25%;font-size:103%;" | Share of revenue http://classex.uni-passau.de/classex3/pic/role1.png
! style="width:25%;font-size:103%;" | Share of revenue http://classex.uni-passau.de/classex3/pic/role2.png
! style="width:100%;font-size:103%;" | Revenue loss
|- 
! Fixed wage system
! 3.20 €
! 100%
! 0%
! 0%
|- 
! Bonus system
! 1.60 €
! 60%
! 25%
! 15%
|- 
! Share of revenue system
! 0 €
! 20%
! 50%
! 50%
|}

In the table, Share of revenue http://classex.uni-passau.de/classex3/pic/role1.png denotes the principal and Share of revenue http://classex.uni-passau.de/classex3/pic/role2.png the agent.
The agent then chooses his level of effort and consequently the revenue and his disutility from working denoted in €:

{| class="wikitable" style="border:solid 2px #999999;font-size:96%;"
|- class="hintergrundfarbe8"
! style="width:16%;font-size:103%;" | Level of effort
! style="width:16%;font-size:103%;" | Very little
! style="width:16%;font-size:103%;" | Little
! style="width:16%;font-size:103%;" | Medium
! style="width:16%;font-size:103%;" | Hardworking
! style="width:100%;font-size:103%;" | Very hardworking
|- 
! Revenue
! 1.60 €
! 3.20 €
! 4.80 €
! 6.40 €
! 8.00 €
|- 
! Disutility
! 1.00 €
! 1.20 €
! 1.60 €
! 2.20 €
! 3.00 €
|}

This game shows that revenue losses are accepted and that systems allowing the agent to participate in the revenues are chosen despite the revenue losses, because the agent only has an incentive to work hard if he participates substantially in the revenues. Some principals also choose the system with a fixed wage and no participation of the agent. However, the game is not played repeatedly and agents hence do not have to fear for their reputation. Therefore, the level of positive reciprocity is small and results in little effort in the system with a fixed wage.


Centipede Game

Sequential games can be run over more than two rounds. A well-known example for this is the centipede game. In the centipede game, the sum of payoffs for both players increases over a finite and known number of rounds. First of all, player 1 [[File: role1.PNG]] makes a decision. In the next stage, player 2 [[File: role2.PNG]] does so. In each stage, participants choose between two options, either to '''take''', which ends the game and ensures the payoff of that round, or to '''pass''' which delegates the decision to player 2 and increases the payoff.

Concretely, this game is implemented as followes in classEx:

The game starts with a total payoff of 5€. In this stage, player 1 [[File: role1.PNG]] decides whether to '''take''' or '''pass'''. If he '''takes''', [[File: role1.PNG]] receives 4€ and [[File: role2.PNG]] receives 1€. If he chooses to '''pass''' the total payoff increases to 10€ and [[File: role2.PNG]] now has to decide whether to '''take''' or '''pass'''. In this stage, [[File: role2.PNG]] has an advantage. '''Take''' renders a payoff of 8€ for [[File: role2.PNG]] and 2€ for [[File: role1.PNG]]. However, if [[File: role2.PNG]] '''passes''', the total payoff increases to 20€. Now, [[File: role1.PNG]] has the choice again. He can either '''take''' and receive 16€, leaving 4€ for [[File: role2.PNG]]. Or, if he chooses to '''pass''', the game ends with another increase of the total payoff to 40€, giving player 2 [[File: role2.PNG]] 32€ and [[File: role1.PNG]] 8€. Two pairs are randomly drawn and receive a winners' notification with which they can collect their payoff. The lecturer is provided with a graphical illustration of how often the game was terminated with the choice of '''take''' in the respective stages.

Numeric

Labor Contract

Trust Game
In the trust game, player 1 (trustor) can can decide whether to transfer none, some or all of her endowment to player 2 (trustee). Transferring the entire endowment is socially optimal because the transferred amount is multiplied by the experimentor. Player 2 can then decide whether to transfer none, some or all of his endowment back to player 1. Therefore, transferring is only worthwile for the trustor, if the trustee repays the trust and transfers back at least the sent amount.



[[File: Trustred.JPG]]   [[File: trustgreen.JPG]]



'''Implementation in classEx:'''

The input for participants can be implemented by defining the variables <div class="quote">$max=10;, $endow=10; and $multi=3;</div>. Here, the endowment equals 10, the maximum transfer by the trustor equals 10 and the multiplier equals 3. The input decision of [[File: role1.PNG]] is stored by the variable $send;. In the second stage, you need to write following code in a programme field:
<div class="quote">$send=$getPartnerDecision("692#1"); $max=$endow+$send*$multi;</div>
Make sure that you make reference to the correct stage and the correct input field. In this example, the code refers to stage number 692 and input field number 1. The following input by [[File: role2.PNG]] is stored as variable <div class="quote">$sendback.</div> Hence, the amount sent back can be calculated by: <div class="quote">$received=$getPartnerDecision("693#1"); $payoff=$endow-$send+$received.;</div> With this, you can write the following in the text field that is displayed to the trustor:
Of your endow; €, you sent $send; € to [[File: role2.PNG]]. This amount was trippled. [[File: role2.PNG]] sent back $received; € to you."


'''Display of results'''

The results are displayed as a bubble chart on the lecturer's screen

[[File: trustlecturer.JPG]]


Ultimatum Game

In the ultimatum game, player 1 takes the role of the proposer and is endowed with a certain amount. He may then transfer all, some or none of this endowment to player 2.
In the next stage, player 2 then decides whether to accept or reject the proposed division of the pie. If player 2 rejects, both players receive a payoff of zero.

Alternating Offer Bargaining
In contrast to the [[Centipede Game|centipede game]], the total pie shrinks over time in the alternating offer bargaining game. Also, input is numeric.

The game starts with a pie of, for example, 20€.

In stage 1 [[File: role1.PNG]] makes a suggestion on how to divide the pie between both players.

In stage 2, [[File: role2.PNG]] can decide whether to accept the division or not. If [[File: role2.PNG]] does not accept the division, the pie shrinks to 16€ and [[File: role2.PNG]] is then required to make a suggestion on how to divide the remaining pie.

In stage 3, [[File: role1.PNG]] then decides whether to accept or reject the division and, in case of a rejection, makes a new suggestion on how to divide the pie which has now shrunk to 12€.

In stage 4, [[File: role2.PNG]] can decide and if she rejects, the pie shrinks to 8€. She then makes a new suggestion on how to divide this pie.

In stage 5, [[File: role1.PNG]] decides and if he rejects the proposed division, he can make a final suggestion on how to divide the pie which has now shrunk to 4€.

If [[File: role2.PNG]] rejects this final suggestion, both players end up with a payoff of 0€.

Two pairs of players are randomly drawn and receive a winner's notification and a real payoff.

A bubble chart allows lecturer to gain an overview of how high the offers were in the respective stages and to compare the results with theoretic values that would result via backwards induction presuming income maximising behaviour.


Continuous | 2 Roles

Continuous games are not yet implemented in classEx. This will be done in the near future.

Unstructured Bargaining
Continuous games are games in which the sequence of decisions is not determined. Participants are allocated to different roles and matched into pairs. However, there are no rules as to who may make an offer in which stage. In contrast to [[Alternating Offer Bargaining]], bargaining is unstructured here. Both participants can make offers at all times. Participants can always accept an offer or make a different offer.

A buyer [[File: role1.PNG]] is willing to pay a certain amount for a good, ranging between 0€ and 100€. The number is determined randomly and is only known to the buyer [[File: role1.PNG]] but not the seller [[File: role2.PNG]]. The seller [[File: role2.PNG]] faces costs for the production of the good which also lie between 0€ and 100€, are determined randomly and are only known to the seller.
Buyers and sellers are matched to one another randomly. The buyer [[File: role1.PNG]] can make an offer to buy the good for a price that must not be above his willingness to pay. At the same time, the seller [[File: role2.PNG]] can make an offer that cannot be lower than his production costs. If an offer is accepted, the game ends. An offer is updated by issuing a new offer. If players have not reached an agreement after two minutes, the game ends and both receive 0€. In case of an agreement, the buyer [[File: role1.PNG]] receives the difference between his willingness to pay and the price. The seller [[File: role2.PNG]], analogously, receives the difference between his production costs and the price.

The lecturer is provided with graphical results in a scatter plot. The abscissa depicts the buyers' willingness to pay and the ordinate displays the costs of the sellers. An '''x''' indicates that an agreement was reached. An '''o''' shows that no agreement was reached. Here, one can see efficiency losses that result from strategic offers.


Dutch Auction
The dutch auction is a variation of the [[Common Value Auction]]. For the description of the game, please see [[Common Value Auction]].

The difference between the American and the Dutch auction is that in the case of a Dutch auction, the bank pays an equilibrium interest rate for all bids and not the interest rate it offered for each bid.

Double Auction 


Often, markets are characterised by the fact that sellers and buyers can make public offers instead of negotiating bilaterally. In one of the first experimental studies on this, Vernon Smith (Journal of Political Economy 1962) showed that prices quickly converge to a level that is predicted for competition and income maximisation. Further studies have exhibited that competition crowds out other factors such as the desire to obtain a monopoly rent or the aim to achieve an equal split of the revenue between buyers and sellers.

A double auction is marked by an environment in which buyers and sellers can make public offers. Hence, a buyer [[File: role1.PNG]] can offer to buy a product for a certain price and this offer is then displayed in a list to all participants. Sellers [[File: role2.PNG]] can either accept the offer or also make an offer which is displayed in the list.














