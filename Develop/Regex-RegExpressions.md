# Title (replace with your title)

Validate credit card numbers
## Summary

Credit cards or debit cards are assigned a 16-digit unique identifier, which is stamped in the front of the card. These cards are used all ove the world to make purchases or load funds. Each card has a unique account number and a cardholder name, which is used to prevent fraud or suspicious activities. REGEX is used to validate the 16-digit card numbers by using a few components of REGEX. For example, we can use character classes, quantifiers, and grouping. Visa cards are signified by using a "4" at the beginning of the string and end with a symbol, like this "$". The first number of each visa card is a fixed or constant digit, such as 4, indicating that it is a visa card. Lets take a look at this regular expression for validating credit card numbers: 
Visa Cards:

("4[0-9]{12}(?:[0-9]{3})?$")

MasterCards: 
^(?:5[1-5][0-9]{2}|222[1-9]|22[3-9][0-9]|2[3-6][0-9]{2}|27[01][0-9]|2720)[0-9]{12}$ 
MasterCard numbers(16) either start with the numbers 51 through 55 or with the numbers 2221 through 2720.

Discover: 
Starts with 6011 or 65 and all have 16-digits. 
^6(?:011|5[0-9]{2})[0-9]{12}$

American Express: 
Start with 34 or 37 and all have 15-digits. 
^3[47][0-9]{13}$

**Note combinging a few examples of regex code for different types of credit cards, if you had a logic statement to see what card is being validated, you can use the  OR operator to scan through all regex and find a match to the type of card being used. Example below: 

var acceptedCreditCards = {
  visa: /^4[0-9]{12}(?:[0-9]{3})?$/,
  mastercard: ^(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14})$
  amex: /^3[47][0-9]{13}$/,
  discover: /^65[4-9][0-9]{13}|64[4-9][0-9]{13}|6011[0-9]{12}|(622(?:12[6-9]|1[3-9][0-9]|[2-8][0-9][0-9]|9[01][0-9]|92[0-5])[0-9]{10})$/
};
You can add on other brands in the statement. 

Now lets breakdown the mastercard/Visa card regex code below, please read headings below.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components
Mastercard or Visa card: ^(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14})$
### Anchors
In this Regex example, you will see an achor tag at the beginning of the expression and a dollar symbol at the end of the expression. The anchor tag (^) matches the starting point of the string. The dollar symbol ($), matches the end point of the string. 
### Quantifiers
^(?:4[0-9]{12}(?:[0-9]{3})?|5[1-5][0-9]{14})$
Quatifiers are used in this regex example. Quantifiers are identified by using {} curly braces to indicate that a group of digits should occur a specific amount of times. For example :

{12} and {14}: Specifies that the preceding character or group ([0-9] in this case) must occur exactly 12 times (visacard) or 14 times for the mastercard . This is used after the 4 to ensure there are 12 digits following it. The same for the " {3}, but this is optionally added  digits.

### Grouping Constructs
One grouping construct used in this expression are non back-referenced symbol which is the "?:", this allows to optionally group the next matched values. For example:

4[0-9]{12}(?:[0-9]{3})? - a visacard starting with 4 with 16 digits, optionally follwed by a additional 3 digits

(?:[0-9]{3})

this is creating a 3 didget number between 0 to 9.It will just use the round brackets for grouping that part of the regex without creating a backreference.

### Bracket Expressions
We have a few bracket notations in this regex example, bracket notation is quite simalar to the character classes, with a defined set of characters. For example, in this example we have "[1-5][0-9]{14}", thismatches a mastercard starting with 5 and the second digit should be between 1 and 5 [1-5].

### Character Classes
Character classes allow you to define characters that will be matched, such as letters or numbers. In this example we are just using numbers, so we use the \d to match any digit between 0 and 9. If we were using letters, it would be defined as follow:
(a-zA-Z) this allows letters between "a to z" and also the upper case of those letters. In this example we are using bracket notation to define the numeric pattern: The curly braces with the number 14 in between means exaclty 12 numeric characters, each ranging from 0 to 9 will match. 

[0-9]{12}

Pass: 012345678943
Failed: 01
Failed: 0123577

### The OR Operator
We compare the two types of card, in this example we have the visa card starting with "4" to identify it as a visa card, then we have the mastercard which is identify with a "5" at the beginning of the regex. The OR operator is used by including "|" symbol between the two types of cards. 

### Flags
There are no flags added to this expression. Flags affect the behavior of the regex engine that modify the way the pattern is matched. Different programming languages and regex libraries support different set of flags. Here are some examples:

/pattern/i - this flag makes the pattern match case-insensitively. 
/pattern/g - searches all matches, not just the first found match, think of it as globally. 
/pattern/m - this flag matches the start and end of each line within a input string 
 **Refer to this link to get more details on other flags:
 https://www.codeguage.com/courses/regexp/flags

### Character Escapes
There are no character escapes included in this regex example. We do not have any literal statements add in the defined expression. Character escapes use back slashes (\) to indicate that a character should be treated literally, rather than a special character. 

## Author
Abigail Burtley
Email: abigailtop95@yahoo.com
Github: https://github.com/Ariesscode/REGEX_RegExpressions/commits/main