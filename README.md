
 
1	INTRODUCTION
#1	This document provides a comprehensive and detailed architectural overview of the system, using a number of different architectural views to depict different aspects of the system. It is intended to capture and convey the significant architectural decisions that have been made on the system.
#2	The system is a Myers-Briggs-Type Indicator test which is an introspective self-report questionnaire. There are 70 questions which will indicate differing psychological preferences in how people perceive the world around them and make decisions. It is a platform independent, browser independent web application which is made using HTML, CSS, JavaScript and Bootstrap. There is no specific age group for the questionnaire. Anybody who wants to know their personality can take up the quiz and know their type. A further details about the personality type can also be founf using the “Know More” link. 
1.1	PURPOSE
a.	The purpose of the document is to give a basic overview of how the application will be, who will benefit from it, the technical aspects, where to find and correct them.
b.	The intended audience for this document is the following individual/group:
•	Enterprise architecture
•	Project Manager and Project Team
•	Build Team
•	Support Team
1.2	AUDIENCE
This document is targeted for technical readers who will maintain the MBTI test application. It is expected that the user has some technical background related to the technologies and terminologies given below:
•	HTML
•	CSS
•	Pagination
•	JavaScript
•	Bootstrap
•	Serialization

1.3	SCOPE
The scope of the Myers-Briggs Type Indicator test includes: -
a.	To make people understand about different psychological types and thus show how useful they are;
b.	To explain them the essence that the theory is much seemingly random variation in the behaviour is actually quite orderly and consistent, being due to basic differences in the ways individuals prefer to use their perception and judgment. 
c.	This comes with a huge set of benefits like one can play with individual strengths, and enable self understanding and so to reduce stress.
d.	Of the personality types there is no type which is best and no type which is worst, just different thinking skills and emotional intelligence.
1.4	DEFINITIONS, ACRONYMS AND ABBREVIATIONS
•	MBTI-Myers Briggs Type Indicator
•	E,e :-Extraversion
•	S,s :-Sensing
•	T, t :- Thinking 
•	J, j:- Judging
•	I, i:- Introversion
•	N,n:- Intuition
•	F,f:- Feeling
•	P,p:-Perceptiom
•	i.e:-that is
•	HTML:-Hypertext Markup Language
•	CSS:- Cascading Stylesheet

1.5	OVERVIEW
Myers-Briggs Type Indicator (MBTI) Test based on the theory of psychological types described by C. G. Jung. The essence of the theory is that much seemingly random variation in the behavior is actually quite orderly and consistent, being due to basic differences in the ways individuals prefer to use their perception and judgment.
"Perception involves all the ways of becoming aware of things, people, happenings, or ideas. Judgment involves all the ways of coming to conclusions about what has been perceived. If people differ systematically in what they perceive and in how they reach conclusions, then it is only reasonable for them to differ correspondingly in their interests, reactions, values, motivations, and skills."
In developing the Myers-Briggs Type Indicator [instrument], the aim of Isabel Briggs Myers, and her mother, Katharine Briggs, was to make the insights of type theory accessible to individuals and groups. They addressed the two related goals in the developments and application of the MBTI instrument:
The identification of basic preferences of each of the four dichotomies specified or implicit in Jung's theory results in the identification of the 16 distinctive personality types that result from the interactions among the preferences.
The 16 types are typically referred to by an abbreviation of four letters—the initial letters of each of their four type preferences (except in the case of intuition, which uses the abbreviation "N" to distinguish it from introversion). For instance:

    ESTJ: extraversion (E), sensing (S), thinking (T), judgment (J)
    INFP: introversion (I), intuition (N), feeling (F), perception (P)
These abbreviations are applied to all 16 types.
So, there is a questionnaire which will have two options each of which will have one of  the above dichotomies. The person will take the questionnaire and submit it. He/She will get the result  in an instant in the same webpage they submitted by scrolling down. There will be a link which will give a more detailed version of the personality type in another web page.
 
2	SYSTEM OVERVIEW
#1	The basic questionnaire is made in a HTML document and are linked with CSS, JavaScript and Bootstrap. The basic calculation take place in the JavaScript document using different functions, methods and variables. CSS adds styling to the web application.
2.1	CHARACTERISTICS
#2	The system has different modules, functions and high -level data flow which enables it :
	to operate in real-time or in bursts,
	the nature of the interface to the users of the system
	a large number of concurrent users
	to be highly resilient or fault tolerant
	to provide security features to protect data
	to be scaleable and easily maintainable in the future
	to have any special back-up facilities to protect important data.
2.2	SYSTEM ARCHITECTURE
The implementation of the MBTI test is as follows:
 

 

The user will have the MBTI test questionnaire on a HTML page which will be linked with some CSS files for styling. Each question will have two options with each having a particular “dichotomy” of the eight (extraversion (E), sensing (S), thinking (T), judgment (J) introversion (I), intuition (N), feeling (F), perception (P)).
Each of these options (which are eventually a particular trait) will behave as a weight and the user’s response to each question will be recorded. The chosen option will increment the particular dichotomies and hence dominant 4 out of the 8 will be found out. These 4 different traits will have a combination of 16 different personality types.
All these calculations will be done in JavaScript using different functions which will be described in the section below: -
Index.html- Web Interface
A simple web interface should be provided.  The user should be able to select the option he/she desires. He/she should be able to submit his responses as well as resume or restart at will. The user should be able to understand the web page and should easily interact with it.
This is also the page where the result will occur. Bootstrap is used to make the result turn into charts and graphs. It will also contain a link which will redirect to another webpage with more details about the particular personality test. 
 

 
For example see the question no. 3 which “Is it worse to:” which has two options 
•	Have your “head in the clouds”
•	Be “in a rut”
Each of the option has a value from e, s, t, j, i, n, f, p. the 1st option has the value “s” and the 2nd option has value “n” which signifies sensing and intuition.
So, the person who selects 1st option will increment the s count in his/her personality and same for n.
After 70 questions, the dominant traits will be identified and hence the personality type will be given. 


Index.js – The JavaScript doc
It will contain different functions in a module named MbtiModule. On the event of clicking of submit button the functions in the module will work.
The following are the functions:
resetScores
It will reset the count the of variables to 0 and everything else will be reset to null.

getScores
It will search for the checked radio buttons and take their value and increment the count of value. It is the function which actually takes the input given by the user and convert it into a meaningful value.
Input
Checked radio buttons.
Output
Count of different variables(e,s,t,j,I,n,f,p)
Attributes
The input value from the checked buttons, variables

calculatePercentage
It will take the count of the variables and calculate the percentage. The percentage will be calculated according to the no of occurrence of each variable.
Input
Count of the variables
Output
Percentage of each variable

createCharts
This function will help in creating the charts via which the results will be shown. Since the variables are 4 set of opposite pairs, this will indicate in which of the trait is the person more inclined to. And it will show that in a tabular manner using bootstrap.
Input
The percentage value of each variable
Output
The variable percentage in a graphical representation.


showResults
This function will show actually which are the 4 main traits which makes the personality of a person different from one other. It will compare between opposite pairs and show only that which is dominant. 
For example, if a person has more E than I, more S than N, more T than F, more J than P; then the person will have a personality type ESTJ. So, the result will show Type ESTJ also called The Guardian, what is extraverted and what is introverted, the total percentage of people (rough idea) in this category and the most common characteristics.
Output
Personality type, characteristics, also known as, total percentage of people like these in the world.
 
3	FURTHER WORK
•	Validation parameters need to be set. All the questions must be answered for getting the result.
•	Pagination library instead of putting all the questions on a same page should be used.
•	State of active question should be made, so as to make sure the quiz is not incomplete.
•	States to maintain whether the quiz has started, taken already, finished, or incomplete. Also state of the currently active question should be maintained so if wished to resume at a later time, it could known where to look.
•	Type data should be segregated in a separate JS file (Called a model). Similarly the functions reset(), getscores and calculate should be segregated in a controller.js. Functions createchart and showresult should be in the view.js.
•	The naming convention: <mvctype>_<modulename>.<extn> should be used. eg. controller_mbtitest.js, view_mbtitest.js, model_mbtitest.js.
•	No serialization in the JS functions. In this case, for example if the app encounters an exception in the calculate function, it will still render the chart and show results, with probably default/uninitialized/garbage values depending upon its declaration type. Also these functions are not encapsulated, so they can call each other irrespective of order. That can lead to a lot of leaks. Callbacks to serialize the execution should be used. 
•	No randomization in the quiz options, so the results will always be the same. at least five options to each question should be made to get a more randomized data set, so that a classifier with multiple personas could be used later.
•	Results should be separated into a different page. OR displayed using callback, so that the result parameters can be sent to any API/page outside the scope of the current page.
•	State of results with the options chosen should be saved. They should be written into a JSON/CSV file if possible during the execution of show results function.  This is useful for building the data dictionary for TF later.  

4	REFERENCES

•	https://www.myersbriggs.org/my-mbti-personality-type/mbti-basics/home.htm?bhcp=1
•	https://en.wikipedia.org/wiki/Myers%E2%80%93Briggs_Type_Indicator
•	https://www.w3schools.com/jsref/prop_radio_checked.asp
•	https://www.w3schools.com/jsref/dom_obj_htmlcollection.asp
•	https://www.w3schools.com/bootstrap/bootstrap_ver.asp
•	https://www.w3schools.com/bootstrap/bootstrap_pagination.asp
•	https://stackoverflow.com/questions/8206565/check-uncheck-checkbox-with-javascript-jquery-or-vanilla
•	https://stackoverflow.com/questions/1423777/how-can-i-check-whether-a-radio-button-is-selected-with-javascript
•	https://www.typeform.com/help/create-personality-quiz/
•	https://www.dragonflycave.com/free-quiz-scripts




