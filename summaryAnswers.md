# Summary Answers

## BooleanOperatorsTest
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
   * To know how to perform basic boolean operations as well as how bitwise operators behave with boolean values
   * [Bitwise and Logical operators](https://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html#jls-15.22.2)
2. Why the test failed at first?
   * The expected output was not there
3. Why you corrected the test that way?
   * I put the boolean result to make the test pass
4. Do you have further questions on this knowledge point?
   * None

## CharTypeTest
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
   * To learn about special character literals that need to be escaped
   * [Escape Sequences](https://docs.oracle.com/javase/tutorial/java/data/characters.html)
2. Why the test failed at first?
   * The expected output was not there
3. Why you corrected the test that way?
   * I put the correct escaped character literal
4. Do you have further questions on this knowledge point?
   * None

## FloatingTypeTest
   * should_not_get_rounded_result_if_convert_floating_number_to_integer
      1. What is the knowledge point of the test? Where is the official document to the knowledge point?
         * To see how Java handles converting a floating number to an integer.
         * [5.1.3. Narrowing Primitive Conversion](https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.1.3)
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * The answer I put was 2: the value of variable floatingPointNumber with the .75 being truncated
      4. Do you have further questions on this knowledge point?
   * should_judge_special_double_cases
      1. What is the knowledge point of the test? Where is the official document to the knowledge point?
         * To see how -Infinity, +Infinity, and NaN are produced and represented in Java.
         * [4.2.3 Floating-Point Types, Formats, and Values](https://docs.oracle.com/javase/specs/jls/se6/html/typesValues.html)
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * In filling up the isNan method, I initially put
         ```java
            return realNumber == Double.NaN;
         ```
         but that answer was wrong since ```Double.NaN!=Double.NaN```.
         * So I just used the existing method ```Double#isNan``` as an alternative.
         * I used a similar method ```Double#isInfinite``` to fill up the isInfinity method.
      4. Do you have further questions on this knowledge point?
         * None
   * should_not_round_number_when_convert_to_integer
      1. What is the knowledge point of the test? Where is the official document to the knowledge point?
         * Converting float to int does not round the decimal places up. Instead, the decimal places are just truncated.
         * [5.1.3. Narrowing Primitive Conversion](https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.1.3)
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * The answer I put was 2: the value of variable floatingPointNumber with the .75 being truncated
      4. Do you have further questions on this knowledge point?
         * None
   * should_round_number
      1. What is the knowledge point of the test? Where is the official document to the knowledge point?
         * Since converting float to int does not round the decimal places up, a different method must be used to round the float numbers.
         * [Math#round](https://docs.oracle.com/javase/7/docs/api/java/lang/Math.html#round(double))
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * I used ```Math#round``` to be able to round floatingPointNumber
      4. Do you have further questions on this knowledge point?
         * None

## IntegerTypeTest
   * I am going to group the answers to these questions
      * Questions
         * should_get_range_of_primitive_int_type
         * should_get_range_of_primitive_short_type
         * should_get_range_of_primitive_long_type
         * should_get_range_of_primitive_byte_type
      * Answer
         1. What is the knowledge point of the test? Where is the official document to the knowledge point?
            * The range and sizes of different data types.
            * How to represent those minimum and maximum sizes in hexadecimal and why they are represented as such.
            * To learn about signed number representations.
            * (Primitive Data Types)[https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html]
         2. Why the test failed at first?
            * The correct output was not there
         3. Why you corrected the test that way?
            * I used the available ```MAX_VALUE``` and ```MIN_VALUE``` constants in the wrapper classes for the primitive data types
         4. Do you have further questions on this knowledge point?
            * None
   * I am going to group the answers to these questions
      * Questions
         * should_overflow_silently
         * should_underflow_silently
      * Answer
         1. What is the knowledge point of the test? Where is the official document to the knowledge point?
            * To show that errors do not occur when an overflow or underflow happens
            * [5.1.3. Narrowing Primitive Conversion](https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.1.3)
         2. Why the test failed at first?
            * The correct output was not there
         3. Why you corrected the test that way?
            * ```Integer.MIN_VALUE + 1 == Integer.MAX_VALUE```
            * ```Integer.MAX_VALUE + 1 == Integer.MIN_VALUE```
         4. Do you have further questions on this knowledge point?
            * None
   * I am going to group the answers to these questions
      * Questions
         * should_throw_exception_when_overflow
         * just_prevent_lazy_implementation
      * Answer
         1. What is the knowledge point of the test? Where is the official document to the knowledge point?
            * Since errors do not occur when an overflow or underflow happens, we need to use a different method that produces errors.
            * (Math#addExact)[https://docs.oracle.com/javase/8/docs/api/?java/lang/Math.html]
         2. Why the test failed at first?
            * The correct output was not there
         3. Why you corrected the test that way?
            * Using ```Math#addExact``` will produce an error when an overflow or underflow occurs. If there is no overflow or
            underflow, the sum of its two parameters is returned.
         4. Do you have further questions on this knowledge point?
            * None
   * should_take_care_of_number_type_when_doing_calculation
      1. What is the knowledge point of the test? Where is the official document to the knowledge point?
         * The result of an integer divided by another integer is also an integer even if the result is assigned to a double.
         * (5.1.2. Widening Primitive Conversion)[https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.1.2]
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * I removed the decimal places from the result. 2/3 is 0.667. Removing the decimal places leave 0.
      4. Do you have further questions on this knowledge point?
         * None
   * should_truncate_number_when_casting
      1. What is the knowledge point of the test? Where is the official document to the knowledge point?
         * A narrowing of int to short loses high bits
         * [5.1.3. Narrowing Primitive Conversion](https://docs.oracle.com/javase/specs/jls/se7/html/jls-5.html#jls-5.1.3)
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * My answer is in hexadecimal to more clearly show how the answer is derived from the integer variable.
      4. Do you have further questions on this knowledge point?
         * None
   * I am going to group the answers to these questions
      * Questions
         * should_increment
         * should_increment_2
      * Answer
         1. What is the knowledge point of the test? Where is the official document to the knowledge point?
            * The prefix version (++result) evaluates to the incremented value, whereas the postfix version (result++) evaluates to the original value
            * (The Unary Operators)[https://docs.oracle.com/javase/tutorial/java/nutsandbolts/op1.html]
         2. Why the test failed at first?
            * The correct output was not there
         3. Why you corrected the test that way?
            * To show the value of the prefix and postfix version of the ++ operator when a value is assigned to be its result.
         4. Do you have further questions on this knowledge point?
            * None
