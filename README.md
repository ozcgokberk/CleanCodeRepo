# CleanCodeRepo
This repo contains sumamry of Clean Code book by Robert C. Martin

Chapter 1:
Remember that code is really the language in which we ultimately express the
requirements. We may create languages that are closer to the requirements. We may
create tools
that help us parse and assemble those requirements into formal structures. But we
will never eliminate necessary precision—so there will always be code.
We know good code matters because we’ve had to deal for so long with its lack.
- What is clean code?
Code should be "elegant", "efficient" said Bjarne Stroustrup. 
Clean code should be simple and direct -Grady Booch.
Clean code can be read and enhanced by a developer than its original author. -Dave Thomas.
Clean code alwasy looks like it was writeen by someone who cares.
Contains no dıplication -Ron Jeffries
- The Boy Scout Rule :
"Leave the campground cleaner than you found it."

- Chapter 2 : Meaningful Names
-Use intention-revealing names.
int d ❌
int elapsedTimeInDays ✅
-Make meaningful distinctions.
string date1, date2 ❌
string startDate, endDate ✅
-Choose descriptive and unambiguous names.
string sd, ed; ❌
string startDate, endDate;✅

-Use pronounceable names
private Date genymdhms;❌
private Date generationTimestamp;✅
-Use searchable names
for (int j=0; j<34; j++) {
s += (t[j]*4)/5;
}❌

int realDaysPerIdealDay = 4;
const int WORK_DAYS_PER_WEEK = 5;
int sum = 0;
for (int j=0; j < NUMBER_OF_TASKS; j++) {
int realTaskDays = taskEstimate[j] * realDaysPerIdealDay;
int realTaskWeeks = (realdays / WORK_DAYS_PER_WEEK);
sum += realTaskWeeks;
}✅
-Member prefixes:
-m_dsc = name ❌
this.description = description ✅
-Use Comment lines.
string requestId; ❌
string requestId; // must be unique✅

-Use nouns for classes, packages, and variables.
class Account, AddressParser✅
class Manager,Processor,Data ❌

-Use verbs/verb phrases for functions
function getAccounts✅
-Add A Meaningful Context
Our goal, as authors, is to make our code as easy as possible to understand. We want
our code to be a quick skim, not an intense study. We want to use the popular paperback
model whereby the author is responsible for making himself clear and not the academic
model where it is the scholar’s job to dig the meaning out of the paper.

- Chapter 3 Functions:
-A function should be readable from top to bottom, as a paragraph.
-A set of functions should be readable from top to bottom, as a set of paragraphs.
-Keep functions small — short (Ideal: 4 lines, Maximum: 60 lines, the whole function must fit into the screen, so that it’s easy to read without vertical scrolling) and not too wide (Up to 70 to 120 characters, it’s easy to read the whole line without horizontal scrolling).
-A function should remain at a constant level of abstraction. It shouldn’t deal with both low level and high-level stuff at the same time.
-Avoid duplications (DRY — Don’t Repeat Yourself).
-A function should do only one thing (Keep it atomic). Avoid causing side effects (Do what its name suggests and nothing else).
-Error handling is one thing. Keep functions that do only that. Start them with try and end with catch and/or finally.
-Use try/ catch instead of conditions if possible (Asking for forgiveness is easier than requesting permission).
-At lower levels, throw exceptions instead of returning error codes.
-Avoid nested control structures. Replace such scenarios with functions or alternative strategies.
-Avoid switchstatements (Hint: use polymorphism and bury the switch statement in an abstract factory).
Avoid using boolean variables as function arguments. Using booleans with other arguments usually means that the function does more than one thing. Always split such functions into smaller functions.
- Chapter 4 Comments: 
- Always try to explain yourself in code. (Don’t use a comment when you can use a well named Function or a Variable)
- Don't be redundant.

- Don't use closing brace comments.
- Don't comment out code. Just remove. "Dont comment bad code rewrite it" -Brian W.
- Use as explanation of intent.
- Use as clarification of code.
- Use as warning of consequences.

- Chapter 5 Formatting:
