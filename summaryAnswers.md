#Summary Answers

##BooleanOperatorsTest
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
   * To know how to perform basic boolean operations as well as how bitwise operators behave with boolean values
   * [Bitwise and Logical operators](https://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html#jls-15.22.2)
2. Why the test failed at first?
   * The expected output was not there
3. Why you corrected the test that way?
   * I put the boolean result to make the test pass
4. Do you have further questions on this knowledge point?
   * None

##CharTypeTest
1. What is the knowledge point of the test? Where is the official document to the knowledge point?
   * To learn about special character literals that need to be escaped
   * [Escape Sequences](https://docs.oracle.com/javase/tutorial/java/data/characters.html)
2. Why the test failed at first?
   * The expected output was not there
3. Why you corrected the test that way?
   * I put the correct escaped character literal
4. Do you have further questions on this knowledge point?
   * None

##FloatingTypeTest
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
         *
      2. Why the test failed at first?
         * The correct output was not there
      3. Why you corrected the test that way?
         * I used ```Math#round``` to be able to round floatingPointNumber
      4. Do you have further questions on this knowledge point?
         * None

##IntegerTypeTest