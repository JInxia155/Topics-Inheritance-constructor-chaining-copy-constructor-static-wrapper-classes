Download Link : https://programming.engineering/product/topics-inheritance-constructor-chaining-copy-constructor-static-wrapper-classes/

# Topics-Inheritance-constructor-chaining-copy-constructor-static-wrapper-classes
Topics: Inheritance, constructor chaining, copy constructor, static, wrapper classes
Problem Description

Help Darryl keep track of his warehouse of paper products! Due to the new computer software poorly

written in C and his boss Michael making it impossible for him to work in the warehouse by adding in his

golden tickets to random shipments, Darryl is unable to keep track of his stock in the warehouse. Help

him by rewriting his software in clean Java!

Solution Description

You will implement 5 classes: PaperProduct.java, PhotoPaper.java, GoldenTicket.java,

DiscountedPaper.java, and Warehouse.java.

Note:

1. All variables should be inaccessible from other classes and must require an instance to be

accessed through, unless specified otherwise.

2. All methods should be accessible from everywhere and must require an instance to be accessed

through, unless specified otherwise.

3. Use constructor and method chaining whenever possible! Ensure that your constructor chaining

helps you reduce code reusage!

4. Reuse code when possible. Helper methods are optional.

5. All floating point values must be printed to only 2 decimal places, with rounding.

6. Make sure to add all Javadoc comments to your methods and classes!

PaperProduct.java

This file will store details about a paper product in general. We will create multiple child classes to

specialize these products.

Variables:

name – a String representing the name of the product at a given instance. An invalid value

should default name to “A4”. The value is invalid if name is an empty String or null. This value

cannot be changed once set.

numberOfSheets – an int representing the number of sheets of paper present in this

product. An invalid value should default this field to 500. The value is invalid if it is negative.

weightOfUnitSheet – a double representing the weight, in grams, of one sheet of the

paper product. An invalid value should default this field to 0.25. The value is invalid if it is

negative. This value cannot be changed once set.

totalProductsToShip – an int representing the total number of PaperProduct that

can be shipped. This field should be shared across multiple instances. It must have an initial

value of 10.

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

o Note: This field should only decrease when product is shipped and should never be negative.

COST_PER_GRAM – a constant representing the cost per gram of any product, with the value

0.025. This field should be accessible everywhere.

Constructor(s):

A constructor that takes in name, numberOfSheets, and weightOfUnitSheet.

A constructor that takes in name and numberOfSheets, and defaults

weightOfUnitSheet to 0.25.

A constructor that takes in name, and defaults numberOfSheets to 500 and

weightOfUnitSheet to 0.25.

A copy constructor that deep copies all instance fields from the old object to the new object.

Methods:

totalWeight

o Returns the total weight of the PaperProduct.

totalCost

o Returns the total cost of the PaperProduct.

paperString

o Returns a String representation of the PaperProduct in the following format:

“<totalWeight>g of <name> for $<totalCost>”

ship

o Takes in the name of the company to ship to as a parameter.

o If totalProductsToShip does not equal 0, return a String in the following format:

“Shipped <totalWeight>g of <name> for $<totalCost> to

<company>.”

o

If totalProductsToShip equals 0, return a String in the following format:

“Cannot ship any items, Warehouse is empty!”

o

Make sure to update all relevant variables in this method (decrement the number of

products to ship by 1).

Getters for name, numberOfSheets, weightOfUnitSheet, and

totalProductsToShip.

Setter for numberOfSheets. Do NOT write a setter for totalProductsToShip.

PhotoPaper.java

This file will store details about the photo paper stock in the warehouse. It is a child class of

PaperProduct.

Variables:

glossiness – a double representing the glossiness of the photo paper in the range [0, 100].

If an invalid value is entered, the value of this field should default to 70.

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

Constructor(s):

A constructor that takes in name, numberOfSheets, weightOfUnitSheet, and

glossiness.

A constructor that takes in name and numberOfSheets, and defaults glossiness to 70

and all other fields to their default value as defined in PaperProduct.

A constructor that takes in name, and defaults glossiness to 70 and all other fields to their

default value as defined in PaperProduct.

A copy constructor that deep copies all instance fields from the old object to the new object.

Methods:

photoString

o Returns a String representation of the PhotoPaper in the following format:

“<glossiness>% glossy and <totalWeight>g of <name> for

$<totalCost>”

shipPhoto

o Takes in the name of the company to ship to as a parameter.

o If totalProductsToShip does not equal 0, return a String in the following format:

“Paper is <glossiness>% glossy. Shipped <totalWeight>g of

<name> for $<totalCost> to <Company>.”

o

If totalProductsToShip is 0, return a String in the following format:

“Paper is <glossiness>% glossy. Cannot ship any items,

Warehouse is empty!”

o

Make sure to update all relevant variables in this method.

▪ Keep in mind that the variables may be private in the super class, but they

should be able to be modified through a publicly available method if chained

correctly.

Getter and setter for glossiness.

Reuse code if possible.

GoldenTicket.java

This file will store details about golden tickets that customers can use with the discounted paper stock.

Variables:

catchphrase – a String object that represents the catchphrase printed on the ticket! An

invalid value should default catchphrase to “Congrats!”. The value is invalid if

catchphrase is an empty String or null.

discount – a double representing the discount offered by the ticket, in percent, in the range

(0, 25]. If an invalid value is entered, then this field should default to 15.0.

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

Constructor(s):

A constructor that takes in catchphrase and discount.

Methods:

ticketString

o Returns a String representation of the GoldenTicket in the following format:

“Golden Ticket with a <discount>% discount! <catchphrase>”

Getters and setters for catchphrase and discount.

DiscountedPaper.java

This file will store details about the discounted paper stock in the warehouse. It is a child class of

PaperProduct.

Variables:

discount – a double representing the discount of the paper product, in percent, in the

range (0, 50]. If an invalid value is entered, then this field should default to 15.0.

ticket – a GoldenTicket object representing whether this product has a golden ticket

attached to it. It has a default value of null.

Constructor(s):

A constructor that takes in name, numberOfSheets, weightOfUnitSheet, discount,

and ticket.

A constructor that takes in name and numberOfSheets, and defaults discount to 15,

ticket to null, and all other fields to their default value as defined in PaperProduct.

A constructor that takes in name, and defaults discount to 15, ticket to null, and all other

fields to their default in PaperProduct.

A copy constructor that deep copies all instance fields from the old object to the new object.

Methods:

discountedCost

o Calculate and return the total cost after the discount.

o If there is a GoldenTicket attached, also apply the golden ticket discount to the

discounted paper’s already discounted cost.

shipDiscounted

o Takes in the name of the company to ship to as a parameter.

o If totalProductsToShip does not equal 0, return a String in the following format:

“Shipped <totalWeight>g of <name> for $<totalCost> to

<company>. The total cost after the discount is

<discountedCost>.”

o

If totalProductsToShip is 0, return a String in the following format:

“Cannot ship any items, Warehouse is empty! The total cost

after the discount is <discountedCost>.”

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

o

Make sure to update all relevant variables in this method.

▪ Keep in mind that the variables may be private in the super class, but they

should be able to be modified through a publicly available method if chained

correctly.

botherAccounting

o Returns a String representation of the discounting of this product as an entry for the

accounting department in the following format:

“Discounted Paper Product:

Original Cost: <original cost>

Final Cost: <final cost>

Original Discount: <original discount>%

Golden Ticket Discount: <golden ticket discount>%”

o If there is no Golden Ticket, then the Golden Ticket discount should be 0.

Getters and setters for discount and ticket.

Reuse code if possible.

Warehouse.java

This is a Driver file to run all the above classes! Use this to test your code.

Create at least 2 PaperProduct, 2 PhotoPaper, 2 DiscountedPaper, and 1

GoldenTicket.

Use the copy constructors at least once. Try modifying the objects to see if you have deep

copied properly.

Call the relevant ship methods on each of your PaperProduct and its children’s objects and

print the results.

Call botherAccounting on all DiscountedPaper and print the result.

These tests and the ones on Gradescope are by no means comprehensive, so be sure to write

your own test cases!

Checkstyle

You must run checkstyle on your submission (To learn more about Checkstyle, check out cs1331-style-

guide.pdf under the CheckStyle Resources module in Canvas.) The Checkstyle cap for this assignment is

15 points. This means there is a maximum point deduction of 15. If you don’t have Checkstyle yet,

download it from Canvas → Modules → CheckStyle Resources → checkstyle-8.28.jar. Place it in the same

folder as the files you want to run Checkstyle on. Run Checkstyle on your code like so:

$ java -jar checkstyle-8.28.jar yourFileName.java

Starting audit…

Audit done.

The message above means there were no Checkstyle errors. If you had any errors, they would show up

above this message, and the number at the end would be the points we would take off (limited by the

Checkstyle cap). In future assignments we will be increasing this cap, so get into the habit of fixing these

style errors early!

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

Additionally, you must Javadoc your code.

Run the following to only check your Javadocs:

$ java -jar checkstyle-8.28.jar -j yourFileName.java

Run the following to check both Javadocs and Checkstyle:

$ java -jar checkstyle-8.28.jar -a yourFileName.java

For additional help with Checkstyle see the CS 1331 Style Guide.

Turn-In Procedure

Submission

To submit, upload the files listed below to the corresponding assignment on Gradescope:

PaperProduct.java

PhotoPaper.java

GoldenTicket.java

DiscountedPaper.java

Warehouse.java

Make sure you see the message stating the assignment was submitted successfully. From this point,

Gradescope will run a basic autograder on your submission as discussed in the next section. Any

autograder test are provided as a courtesy to help “sanity check” your work and you may not see all

the test cases used to grade your work. You are responsible for thoroughly testing your submission on

your own to ensure you have fulfilled the requirements of this assignment. If you have questions about

the requirements given, reach out to a TA or Professor via the class forum for clarification.

You can submit as many times as you want before the deadline, so feel free to resubmit as you make

substantial progress on the assignment (submit early and often). We will only grade your latest

submission. Be sure to submit every file each time you resubmit.

Gradescope Autograder

If an autograder is enabled for this assignment, you may be able to see the results of a few basic test

cases on your code. Typically, tests will correspond to a rubric item, and the score returned represents

the performance of your code on those rubric items only. If you fail a test, you can look at the output to

determine what went wrong and resubmit once you have fixed the issue.

The Gradescope tests serve two main purposes:

Prevent upload mistakes (e.g., non-compiling code)

Provide basic formatting and usage validation

In other words, the test cases on Gradescope are by no means comprehensive. Be sure to thoroughly

test your code by considering edge cases and writing your own test files. You also should avoid using

Gradescope to compile, run, or Checkstyle your code; you can do that locally on your machine.

Other portions of your assignment can also be graded by a TA once the submission deadline has passed,

so the output on Gradescope may not necessarily reflect your grade for the assignment.

THIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZEDTHIS GRADED ASSESSMENT IS NOT FOR DISTRIBUTION.

ANY DUPLICATION OUTSIDE OF GEORGIA TECH’S LMS IS UNAUTHORIZED.

Allowed Imports

To prevent trivialization of the assignment, you are not allowed to import any classes or packages.

Feature Restrictions

There are a few features and methods in Java that overly simplify the concepts we are trying to teach or

break our auto grader. For that reason, do not use any of the following in your final submission:

var (the reserved keyword)

System.exit

System.arraycopy

Collaboration

Only discussion of the assignment at a conceptual high level is allowed. You can discuss course concepts

and HW assignments broadly, that is, at a conceptual level to increase your understanding. If you find

yourself dropping to a level where specific Java code is being discussed, that is going too far. Those

discussions should be reserved for the instructor and TAs. To be clear, you should never exchange code

related to an assignment with anyone other than the instructor and TAs.

You MAY NOT use code generation tools to complete this assignment. This includes generative AI tools

like ChatGPT.

Important Notes (Don’t Skip)

Non-compiling files will receive a 0 for all associated rubric items

Do not submit .class files

Test your code in addition to the basic checks on Gradescope

Submit every file each time you resubmit

Read the “Allowed Imports” and “Restricted Features” to avoid losing points

Check on Ed Discussion for a note containing all official clarifications and sample outputs

It is expected that everyone will follow the Student-Faculty Expectations document, and the Student

Code of Conduct. The professor expects a positive, respectful, and engaged academic environment

inside the classroom, outside the classroom, in all electronic communications, on all file submissions,

and on any document submitted throughout the duration of the course. No inappropriate language is

to be used, and any assignment, deemed by the professor, to contain inappropriate, offensive

language or threats will get a zero. You are to use professionalism in your work. Violations of this

conduct policy will be turned over to the Office of Student Integrity for misconduct.
