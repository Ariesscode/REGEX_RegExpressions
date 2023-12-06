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
  mastercard: /^5[1-5][0-9]{14}$|^2(?:2(?:2[1-9]|[3-9][0-9])|[3-6][0-9][0-9]|7(?:[01][0-9]|20))[0-9]{12}$/,
  amex: /^3[47][0-9]{13}$/,
  discover: /^65[4-9][0-9]{13}|64[4-9][0-9]{13}|6011[0-9]{12}|(622(?:12[6-9]|1[3-9][0-9]|[2-8][0-9][0-9]|9[01][0-9]|92[0-5])[0-9]{10})$/
};
You can add on other brands in the statement. 

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

### Anchors

### Quantifiers

### Grouping Constructs

### Bracket Expressions

### Character Classes

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
