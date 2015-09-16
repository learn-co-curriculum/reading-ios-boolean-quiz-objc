# `BOOL`ean Quiz

## Objectives

1. Review the nature of `BOOL` primitives.
2. Use the comparison operators which return `BOOL`s.
3. Use the logical operators (`&&`, `||`, and `!`) to combine or invert `BOOL` values.

## `BOOL`

A boolean is binary value expressed in Objective-C as the primitive type `BOOL` which can hold either `YES` or `NO` (true or false) values. Their primary use in programming is in decision making. Booleans are typically created as the result of some comparison or evaluation, and are then assessed to make a conditional choice in the program's behavior. Before discussing conditional flow control, it's important to have a solid understanding of how booleans themselves operate.

```objc
BOOL isYes = YES;
BOOL isNo = NO;
```

A `BOOL` can printed using an `NSLog()` with the format specifier `%d`:

```objc
NSLog(@"isYes: %d", isYes);
NSLog(@"isNo: %d", isNo);
```

### Comparison Operators

A boolean value is returned as the result of any of the six comparison operators in Objective-C: 

| Comparison | Pronunciation              | Description |
|:----------:|:---------------------------|:------------|
| `==` | "is equal to" or "double equals" | Results to `YES` only if the two operands are **exactly** equal in value. |
| `!=` | "is not equal to"                | Results to `YES` only if the two operands are **not exactly** equal in value.
| `<`  | "less than"                      | Results to `YES` only if the value of the left operand is lower than the value of the right operand. |
| `<=` | "less-than-or-equal-to"          | Results to `YES` if the value of the left operand is lower than or the same as the value of the right operand.
| `>`  | "greater than"                   | Results to `YES` if the value of the left operand is higher than the value of the right operand.
| `>=` | "greater-than-or-equal-to"       | Results to `YES` if the value of the left operand is higher than or the same as the value of the right operand.

To capture the result of each of these comparisons into a `BOOL` variable, our implementation might look something like this: 

```objc
BOOL sevenIsEqualToSeven = 7 == 7;
BOOL sevenIsNotEqualToEight = 7 != 8;
BOOL fiveIsLessThanSeven = 5 < 7;
BOOL sevenIsLessThanOrEqualToSeven = 7.0 <= 7;
BOOL eightIsGreaterThanSeven = 8 > 7;
BOOL sevenIsGreaterThanOrEqualToSeven = 7.0 >= 7;
```
We can then use `NSLog()` to print the values to the console:

```objc
NSLog(@"sevenIsEqualToSeven: %d", sevenIsEqualToSeven);
NSLog(@"sevenIsNotEqualToEight: %d", sevenIsNotEqualToEight);
NSLog(@"fiveIsLessThanSeven: %d", fiveIsLessThanSeven);
NSLog(@"sevenIsLessThanOrEqualToSeven: %d", sevenIsLessThanOrEqualToSeven);
NSLog(@"eightIsGreaterThanSeven: %d", eightIsGreaterThanSeven);
NSLog(@"sevenIsGreaterThanOrEqualToSeven: %d", sevenIsGreaterThanOrEqualToSeven);
```
This will print:

```
sevenIsEqualToSeven: 1
sevenIsNotEqualToEight: 1
fiveIsLessThanSeven: 1
sevenIsLessThanOrEqualToSeven: 1
eightIsGreaterThanSeven: 1
sevenIsGreaterThanOrEqualToSeven: 1
```

## Logical Operators

When processing logic, booleans can be evaluated in a few different ways by using the logical operators. In Objective-C, these logical operators are represented by `&&` ("double-ampersand"), `||` ("double-pipe"), and `!` ("the negation operator") respectively.

**Note:** *On the QWERTY keyboard layout, the* `|` *("pipe") symbol is the* `shift` *case on the backslash* `\` *key.*

| Symbol | Logical Operation | Description |
|:------:|:-----------------:|:------------|
| `&&`   | AND | Passes only if **both** conditionals are true. |
| `||`   | OR | Passes if **either** conditional is true. |
| `!`    | NOT | Passes if the **inverse** of the conditional is true (if the conditional is false). |

**Note:** *The single-ampersand* `&` *and single-pipe* `|` *are "bitwise operators" inherited from C. Don't use them—they'll behave in ways you don't expect.*

Any `BOOL` can be defined as the result of evaluating combined conditionals:

```objc
BOOL noAndNo = NO && NO;   // results to NO
BOOL yesOrNo = YES || NO;  // results to YES
BOOL notYes = !YES;        // results to NO
```

The following tables outline how each of the logical operators evaluate:

##### Logical AND (`&&`)

| Condition A | Condition B | = | AND Result |
|:-----------:|:-----------:|:-:|:----------:|
| `NO`        | `NO`        | = | `NO`       |
| `NO`        | `YES`       | = | `NO`       |
| `YES`       | `NO`        | = | `NO`       |
| `YES`       | `YES`       | = | `YES`      |

##### Logical OR (`||`)

| Condition A | Condition B | = | OR Result |
|:-----------:|:-----------:|:-:|:---------:|
| `NO`        | `NO`        | = | `NO`      |
| `NO`        | `YES`       | = | `YES`     |
| `YES`       | `NO`        | = | `YES`     |
| `YES`       | `YES`       | = | `YES`     |

##### Logical NOT (`!`)

| Condition | = | NOT Result |
|:---------:|:-:|:----------:|
| `YES`     | = | `NO`       |
| `NO`      | = | `YES`      |

### Evaluating Variables

Booleans can be used to check other values for existence. If you set a `BOOL` variable to a value or variable that is not `YES` or `NO` it evaluates down to a "true" or "false" answer of whether or not that value or variable is either `0` ("zero") or `nil`. Anything non-zero and non-`nil` will evaluate to `YES`, while anything that is `0` ("zero") or `nil` will evaluate to `NO`.

```objc
BOOL isZero = 0;   // evaluates to NO
BOOL isNil = nil;  // evaluates to NO

BOOL isOne = 1;    // evaluates to YES
BOOL isSeven = 7;  // evaluates to YES
BOOL isNegativeSeven = -7;  // evaluates to YES
BOOL emptyString = @"";     // evaluates to YES
BOOL ponsoExists = [[NSObject alloc] init];  // evaluates to YES
```

## Pity the `BOOL`

![](https://curriculum-content.s3.amazonaws.com/ios/ios-objc-fundamentals-unit/pity_the_bool.jpg)

The rest of the reading is a quiz challenge about how booleans evaluate. Because there are only two values that a boolean can hold, there are two only choices for each question: `YES` and `NO`. Now think like a `BOOL`!


???

# Boolean Quiz

?: 1. `BOOL isYes = YES;`

(X)`YES` ( )`NO`

?: 2. `BOOL isNo = NO;`

( )`YES` (X)`NO`

?: 3. `BOOL yesAndYes = YES && YES;`

(X)`YES` ( )`NO`

?: 4. `BOOL yesAndNo = YES && NO;`

( )`YES` (X)`NO`

?: 5. `BOOL noAndYes = NO && YES;`

( )`YES` (X)`NO`

?: 6. `BOOL noAndNo = NO && NO;`

( )`YES` (X)`NO`

?: 7. `BOOL noOrNo = NO || NO;`

( )`YES` (X)`NO`

?: 8. `BOOL yesOrNo = YES || NO;`

(X)`YES` ( )`NO`

?: 9. `BOOL noOrYes = NO || YES;`

(X)`YES` ( )`NO`

?: 10. `BOOL yesOrYes = YES || YES;` 

(X)`YES` ( )`NO`

?: 11. `BOOL yesOrNoAndNoOrYes = (YES || NO) && (NO || YES);`

(X)`YES` ( )`NO`

?: 12. `BOOL yesAndNoOrNoAndYes = YES && (NO || NO) && YES;`

( )`YES` (X)`NO`

?: 13. `BOOL notYes = !YES;`

( )`YES` (X)`NO`

?: 14. `BOOL notNo = !NO;`

(X)`YES` ( )`NO`

?: 15. `BOOL notNoAndNotYes = !NO && !YES;`

( )`YES` (X)`NO`

?: 16. `BOOL notYesOrNo = !YES || NO;`

( )`YES` (X)`NO`

?: 17. `BOOL notNoOrNo = !(NO || NO);`

(X)`YES` ( )`NO`

?: 18. `BOOL notYesAndNo = !(YES && NO);`

(X)`YES` ( )`NO`

?: 19. `BOOL oneIsOne = 1 == 1;`

(X)`YES` ( )`NO`

?: 20. `BOOL notFortyTwo = 42 != 42;`

( )`YES` (X)`NO`

?: 21. `BOOL lessThan = 6 < 7;`

(X)`YES` ( )`NO`

?: 22. `BOOL lessThanOrEqualTo = 8 <= 7;`

( )`YES` (X)`NO`

?: 23. `BOOL greaterThan = 5 > 5;`

( )`YES` (X)`NO`

?: 24. `BOOL greaterThanOrEqualTo = 5 >= 5;`

(X)`YES` ( )`NO`

?: 25. `BOOL georgeIsBoole = [@"George" isEqualToString:@"Boole"];`

( )`YES` (X)`NO`

?: 26. `BOOL georgeIsGeorge = [@"George" isEqualToString:@"George"];`

(X)`YES` ( )`NO`

?: 27. `BOOL boolIsBOOL = [@"bool" isEqualToString:@"BOOL"];`

( )`YES` (X)`NO`

?: 28. `BOOL boolUpcaseIsBOOL = [[@"bool" uppercaseString] isEqualToString:@"BOOL"];`

(X)`YES` ( )`NO`

?: 29. `BOOL georgeIsNotBoole = ![@"George" isEqualToString:@"Boole"];`

(X)`YES` ( )`NO`

?: 30. `BOOL georgeIsNotGeorge = ![@"George" isEqualToString:@"George"];`

( )`YES` (X)`NO`

?: 31. `BOOL isOne = 1;`

(X)`YES` ( )`NO`

?: 32. `BOOL isZero = 0;`

( )`YES` (X)`NO`

?: 33. `BOOL isNil = nil;`

( )`YES` (X)`NO`

?: 34. `BOOL answer = 42;`

(X)`YES` ( )`NO`

?: 35. `BOOL emptyString = @"";`

(X)`YES` ( )`NO`

?: 36. `BOOL ponsoExists = [[NSObject alloc] init];`

(X)`YES` ( )`NO`


???
