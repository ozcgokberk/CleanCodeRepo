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
Divide ideas vertically.
Vertically dense related code should be shown.
Declare variables near where they will be used.
Dependent functions ought to be near together.
Similar functions ought to be nearby.
Maintain short lines.
Use vertical alignment only.
To correlate objects that are related and to dissociate weakly related ones, use white space.
Keep the indentation intact.

Chapter 6: Objects and data structures
Cover internal organization.
preferred data structures
Avoid hybrid building types (half object and half data).
Should be modest.
Make one move.
only a few instance variables.
The base class shouldn't be aware of its derivatives.
It is preferable to have numerous functions than to pass a function a piece of code to choose a behavior.
Choose non-static methods over static ones.

Chapter 7: Error Handling
The business logic shouldn't be obscured by error handling.
Every method between the throwing method and the handling method must declare checked exceptions as violating the Open/Closed Principle.
Chapter 8: Boundries:

Use "learning tests" to test out third-party code before integrating it into your
codebase. Integration of third-party code should be covered by "boundary tests" so 
that we know if a new version of the library will work as expected. Third-party code 
should be wrapped so as to not expose its externals to your system.
Chapter 9:Test
dirty tests are worse than no tests - they will reduce understanding and take more time to change than the production code
test code must be made to read
a good test follows the FIRST rules:
-fast
-independent
-reliable
-self-validating
-timely

Chapter 10: Classes
a class should have a single reason to change
“A system with many small classes has no more moving parts than a system with a few large classes.”
classes are maximally cohesive if every method manipulates or accesses each instance variable
if a class loses cohesion, split it

Chapter 11 : Systems
Obey the Separation of Concerns principle. Never let convenient idioms lead to
modularity breakdown, e.g. by hard-coding dependencies; the startup process is a 
major concern. Use factories and Dependency Injection (DI), which applies the
Inversion of Control (IoC) principle: Delegate the creation of dependencies to
objects that are specialized to that task (either explicitly or, preferably, via 
suitable constructor parameters or setter methods). This also supports the Single
Responsibility Principle.

Chapter 12:
Simple design rule 1: Runs All the test
First and foremost, a design must produce a system that acts as intended. A system might
have a perfect design on paper, but if there is no simple way to verify that the system actually works as intended, then all the paper effort is questionable.
A system that is comprehensively tested and passes all of its tests all of the time is a testable system. That’s an obvious statement, but an important one. Systems that aren’t testable aren’t verifiable. Arguably,
a system that cannot be verified should never be deployed.
Fortunately, making our systems testable pushes us toward a design where our classes are small and single purpose. It’s just easier to test classes that conform to the SRP. 
Refactoring :
We can increase cohesion, decrease coupling, separate concerns, modularize system concerns, shrink our functions and classes, choose better names,
and so on. This is also where we apply the final three rules of simple design: Eliminate
duplication, ensure expressiveness, and minimize the number of classes and methods.
No Duplication: 
Duplication is the primary enemy of a well-designed system. It represents additional
work, additional risk, and additional unnecessary complexity
To keep this system clean, we should eliminate  the duplication
refactor to separate responsibilities
take pride in workmanship to improve code continuously - the design will emerge
