# Read 08 - Notes: Javascript operators and loops

## Comparison operators
The results of these operators will be a Boolean (True/False)

- `==` : is equal to (checks if values are same)
- `!=` : is not equal to (checks if values are not the same)
- `===` : strict equal to (checks both the value and the data tupe are the same)
- `!==` : strict not equal to (checks both the value and data type are not the same)
- `>` : greater than
- `<` : less than 
- `>=` : greater than or equal to
- `<=` : less than or equal to

## Logical operators
- `&&` : logical AND
   - TT -> True; TF = FT = FF -> False
- `||` : logical OR
   - TT = TF = FT -> True; FF -> False
- `!` : logical NOT
   - !True -> False; !False -> True

## Assignment operators
Assignment operators are used to change/update variables (they are **different** from Arithmetic operators from Read 07 notes).
- `=` : x = y
- `+=` : x = x + y
- `-=` : x = x - y
- `*=` : x = x * y
- `/=` : x = x / y
- `%=` : x = x % y
- `**=` : x = x ** y

## Loops
Allows repeated running of code within the loop so long as conditions are met (i.e. returns true)

### For loops
Used for a definite number of iterations. Often used in conjunction with a counter.
```
for (var i = 0; i < 10; i++){
    document.write(i);
}
```

### While loops
Used for an indefinite number of iterations. Need to mitigate for infinite loops.
```
while (i < 10) {
    msg += i + ' x 5 = ' + (i * 5) + '<br/>';
    i++;
}
```

### Do while loops
Soimiliar to while loop but it will run the statements inside the curly braces at least once, **even if conditions are false**
```
do {
    msg += i + ' x 5 = ' + (i * 5) + '<br/>';
    i++;
} while (i < 1);
```

***
[<<< Back to Main](sangmlee76.github.io/reading-notes/)