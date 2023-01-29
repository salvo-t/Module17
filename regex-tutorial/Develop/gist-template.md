Hello in this tutorial I will show you how to use regular expressions (Regex) with emails. After reading through this tutorial it will be be 10x eaiser to find a specific email in your algorithm.

## Summary

If not familiar regex is is a sequence of characters that defines a specific search pattern. This is the regex I will be using /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/. It looks complicated but it will all of this will make sense.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Looking above at the code this regex componets this whole thing can be broken down into three main groups. Starting with group one ([a-z0-9_\.-]+), first the parentheses represents capturing a group, and the plus to add a second group to the search query. [a-z] is searching for a string that contains lowercase letters a to z. An example that just having a sring like "cat", the length doesnt matter and all the letters are lowercase so it checks out. [0-9] is searching for a string that contains numbers 0 to 9 like "123". Underscore dot hyphen or [_\.-] is included as well search query, an example that would be valid is "__._-". Now adding these all together what can we do? We know that we can look for lowercase letters, numbers 1 to 9, underscores, dots and hyphens. Examples are "j-on_8." or "k1ng-". But remember that it doesnt have to fit all five search querys, it only has to fufill one like "zz", ".", "---". The second group ([\da-z\.-]+) is mostly the same excluding the "\d" this is explained in the character classes but to sum it up it has the same meaning as [0-9]. And the last group ([a-z\.]{2,6}), the only major difference is the ending "{2,6}" these are explained in the quanifiers section. In summery it limits the amount of characters used in the group. I did leave out the @ and "\." but all you have to do is add them between the groups where they belong. So what would a valid regex look like that matches all three groups? Examples are "ky1e_@gmail.com", "999449@1111....", "mike-.@4444.sos" or "a@1.co". I hope this tutorial helped you there is more to learn about regex below.

### Anchors

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Anchors match a position before or after the characters. In this example and in most regex the two anchors you will be using is the "^" at the begining and "$" at the end.

### Quantifiers

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Quanifiers sets limits of the maximum and minimum of the string or group of string. At the end of our example string you see "{2,6}". This quantifier shows us that for group three the minimum and maximum amount of characters we can use being "2-6". The last quantifier is the + sign, it means that the group has one or more matching patterns in the next group. 

### OR Operator

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
An or operator is used when you want a bracket string to meet certain requirements. 
For example using (0|1|2), it will match "0, 1, 2", "2" but not "9", because the or operator can only match what you put in. 

### Character Classes

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
There are many different quantifiers used in regex but in this example I provided it only has two. The first is the "\." this character class is just a literal dot. The second is "\d", meaning digit it matches any arabic number, its just like using [0-9].

### Flags

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Flags are used to define additional functionality to regex, this is done by adding it after the second slash. There are six different flags that can be used or combined to your regex. I will be showing the major three are "g", "i" and "m". G is just a global search of everything in the string. The "i" means that case insensitive will be ingored, so you dont need to specify [a-zA-Z]. Finally "m" is a multi line string input search. All of these flags if used would be added to the  end of the "/" looking like "/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/gmi".


### Grouping and Capturing

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Grouping is very straight forward, each group in the expression is the "()", they are just a contianer for the variables youre searching for. An example is ([a-z0-9_\.-]+). Capturing is a way to treat multiple characters in a single unit, for example "(jon@)" is a sigle group containing a "j", "o", "n" and "@".


### Bracket Expressions

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Bracket expressions are the values inside the brackets in the regex above. For exampel [a-z], the regex can look up any word/letter a to z but it must be lower case unless expressed otherwise. Or another major one is [0-9], this can search up any arabic number. Basically what is inside the brackets is what is being searched.

### Greedy and Lazy Match

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
By default regex will automatically match greedy, meaning as long as possible but using a ? in the regex like ([a-z?]) you can search with lazy. This allows you to search as small as possible for example, if you were looking up "GiovanniReddasIsCool3333@gmail.com" instead of typing all of that out using lazy you can just type "GiovanniR@g.co". The smallest the example allows us to search.  

### Boundaries

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Boundairies are a whole word only search anchor. The example above does not have a boundary, just remember it cannot search any non words like numbers and special characters. Because its a anchor it must be added to the start and the end, for example if I want to search the word "hello", id use "\bHello\b". 

### Back-references

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})\1$/
Back references match the same text as a previous matched group. For example the third group "([a-z\.]{2,6})\1" by using the "\1" it matches the same text from the group.


### Look-ahead and Look-behind

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
Look-ahead and look-behind is a way you can match somthing depending on the context before or after it. Look-ahead or "(?=)" starts at the beginning of a text matching everything after the current position you defined, for example if youre looking up "(?=@windMail)" it will show you every match that comes after "@windMail" like ".com" or ".net". And finally Look-behind or "(?<=)" is the same search feature except it starts at the end of the tezxt and moves backwards from position. Lets just say youre looking up "?<=windMail" with look behind, the position is "@windMail" before it youll find somthing like "RobFord@windMail" or "JesseJames@windMail".

## Author

I am a college full stack programmer and my github is https://gist.github.com/salvo-t
