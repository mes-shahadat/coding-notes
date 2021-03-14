# js numbers




## legal numbers (decimal, exponent), arithmatic opearator (isNaN, infinity), Number(), parseInt(), parseFloat()
## number methods: toString(), toExponential(), toFixed(), toPrecison(), isInteger(), isNaN(), isSafeInteger()
## math methods: min(), max(), round(), floor(), ceil(), random()

<script>

    //you can say declared using numaric literals (below all variables are legal number)

    let num1 = "111";// typeof is string. this is called not a valid number, but this value is not a illigal number. when a value can't be substracted (-), multiplicated (*) or divided (/) with a numaric value, that value is a illigal number.

    let num2 = 111;// typeof is number.

    //decimal. (.) dot is called decimal point. integers with decimal point
    let num3 = 11.45;// typeof is number.

    //exponent (scientific notation to write large digit where e means 10) (5x10^3 = 5x10x10x10 = 5000 = 5e3)
    let num4 = 5e3;// typeof is number.

    let num5 = 10000000000000000000000000000000000000000000000000000000000000000000000000;//larger values are shown as exponent

    //exponent (0.00034)
    let num5 = 34e-5;// typeof is number.

    //declaring with number constructor
    let num6 = new Number(111);// typeof is object












    // + is used for both addition and concatination. so if you add two numaric value where one is string data type, then it will not do addition but will concatinate them and change the output to string
    document.write(10 + "30"); // returns "1030" -> string
    document.write("<br>");






    //in javascript addition starts from left to right. while doing addition operations if string is in left side then + operator will concatinate all of them.
    document.write("hello " + 10 + 20);// returns "hello 1020" -> string
    document.write("<br>");






    //in javascript addition starts from left to right. so, it at first it concated the string with number and changed that to string and concated that string with the other number and return string
    document.write("result: " + 10 + 20);// returns "result: 1020" -> string
    document.write("<br>");






    // -(substraction), *(multiplication), /(division) only works with numaric value, even if the numaric value is in string
    document.write("30" - 10);// returns 20 -> number
    document.write("<br>");






    //you can't substract 10 from hello, so it returned NaN (NaN property indicates that a value is not a legal number)
    document.write("hello " - 10);// returns NaN -> number
    document.write("<br>");






    //multiplication and division works same way (-) substraction, and will return NaN if one of both values is not numaric value
    document.write(10 * "30");// returns 300 -> number
    document.write("<br>");






    //you can't multiply 10 into hello, so it returned NaN (cause one of the value is not a legal number) NaN is not equal to anything
    document.write(10 * "hello ");//returns NaN -> number














    //Infinity:

    //Infinity is displayed when a number exceeds the upper limit of the floating point numbers, which is 1.797693134862315E+308.
    document.write(1.7976931348623157E+10308);//Infinity is a numeric value that represents positive infinity.
    document.write("<br>");



    //-Infinity is displayed when a number exceeds the lower limit of the floating point numbers, which is -1.797693134862316E+308. 
    document.write(-1.7976931348623157E+10308);//-Infinity is a numeric value that represents negative infinity.
    document.write("<br>");


    //like in childhood math class dividing any digit with zero will return infinity
    document.write(5 / 0);
    document.write("<br>");
    document.write(-5 / 0);

















    //global number functions:










    //isNaN (global function). there is also a number method exist called isNaN. isNaN() function returns true if given argument is illegal number (Not a Number). and returns false if given argument is a legal number. it first converts the argument to number the test it.

    let a = 50; // legal number
    let b = "50"; // legal number
    let c = "hello"; // illigal number

    document.write(isNaN(c));













    

    // (useful if you want to convert number inside string into number data type)
    //JavaScript Number() Function function converts the object argument to a number that represents the object's value. If the value cannot be converted to a legal number, NaN is returned. If no argument is provided, it returns 0. If the parameter is a Date object, the Number() function returns the number of milliseconds since midnight January 1, 1970 UTC

    document.write("100: " + Number(100) + "<br>"); // 100
    document.write("'100': " + Number("100") + "<br>"); // 100
    document.write("tue: " + Number(true) + "<br>"); // 1
    document.write("false: " + Number(false) + "<br>"); // 0
    document.write("hello: " + Number("hello") + "<br>"); // NaN
    document.write("new Date(): " + Number(new Date()) + "<br>"); // 1614612589191

















    //online number system converter site: https://codebeautify.org/all-number-converter


    /*
    The parseInt() function parses first number in the string and returns an integer (without decimal values). The radix parameter is used to specify which numeral system to be used to convert to decimal
    
    syntax: parseInt("string", radix(optional)). 
    
    radix -> A number (from 2 to 36) that represents the numeral system to be used. ex: base 2 is called binary, base 8 is called octal, base 10 is called decimal, base 16 is called hexadecimal. a radix of 16 (hexadecimal) indicates that the number in the string should be parsed from a hexadecimal number to a decimal number.
    */

    //If the radix parameter is omitted (without radix parameter), JavaScript assumes the following:

    //The parseInt() function parses a string and returns an integer.
    document.write(parseInt("10") + "<br>"); //10

    //If the string begins with any other value (except for 0x), the default radix will be 10 (decimal). 020 decimal to decimal is 20
    document.write(parseInt("020") + "<br>"); //20

    // it converts 12.00 to decimal
    document.write(parseInt("12.00") + "<br>"); //12
    document.write(parseInt("15.45") + "<br>"); //15

    // Only the first number in the string is returned!
    document.write(parseInt("10 20 30") + "<br>"); //10

    // Leading(on start) and trailing (on end) spaces are allowed. will parse and return 90
    document.write(parseInt("  90  ") + "<br>"); //90

    // If the first non-whitespace character cannot be converted to a number, parseInt() returns NaN.  
    document.write(parseInt("year 10") + "<br>"); //NaN
    document.write(parseInt("10 years") + "<br>"); //10




    //with the radix parameter. if the radix is smaller than 2 or bigger than 36 will return NaN

    //parses 12 octal to decimal
    document.write(parseInt("12", 8) + "<br>"); //10

    //If the string begins with "0x", the radix is 16 (hexadecimal). parses 12 hexadecimal to decimal
    document.write(parseInt("0x12") + "<br>"); //18

    //parses 10 hexadecimal to decimal 
    document.write(parseInt("10", 16) + "<br>"); //16

















    /*
    The parseFloat() function parses a string and returns a floating point number (shorter decimal). This function determines if the first character in the specified string is a number. If it is, it parses the string until it reaches the end of the number, and returns the number as a number, not as a string.

    float: Float is a single precision (32 bit) floating point data type and decimal is a 128-bit floating point data type. Decimal accurately represent any number within the precision of the decimal format, whereas Float cannot accurately represent all numbers.
    */


    // The parseFloat() function parses a string and returns a floating point number
    document.write(parseFloat("10") + "<br>"); //10
    document.write(parseFloat("12.00") + "<br>"); //12.00 == 12
    document.write(parseFloat("15.45") + "<br>"); //15.45

    // Only the first number in the string is returned!
    document.write(parseFloat("10 20 30") + "<br>"); //10

    // Leading(on start) and trailing (on end) spaces are allowed. will parse and return 90
    document.write(parseFloat("  90  ") + "<br>"); //90


    // If the first non-whitespace character cannot be converted to a number, parseFloat() returns NaN.  
    document.write(parseFloat("year 10") + "<br>"); //NaN
    document.write(parseFloat("10 years") + "<br>"); //10

    //If the first value is 0 then ignores 0 returns the real value 20
    document.write(parseFloat("020") + "<br>"); //20
















    //number methods: toString(), toExponential(), toFixed(), toPrecison(), isInteger(), isNaN(), isSafeInteger()




    //toString() method converts number into string. you can use this method to output numbers as hexadecimal(16), octal(8), binary(2). toString() method is also available for array, string, number

    let a = 11;
    document.write(a + "<br>"); // 11 -> number

    document.write(a.toString() + "<br>"); // "11" -> string

    //base 16 is called hexadecimal
    document.write(a.toString(16) + "<br>"); // b -> string (16 means will convert the number to hexadecimal)

    //base 8 is called octal
    document.write(a.toString(8) + "<br>"); // 13 -> string (8 means will convert the number to octal)

    //base 2 is called binary
    document.write(a.toString(2) + "<br>"); // 1011 -> string (2 means will convert the number to binary)











    //In JavaScript, toExponential() is a Number method that is used to convert a number to exponential notation and return its value as a string. .
    //(in argument) an integer between 0 and 20 representing the number of digits in the notation after the decimal point. means the optional argument is an integer specifying the number of digits after the decimal point. If omitted (leave out the argument), it is set to as many digits as necessary to represent the value 

    let a = 58975.998745;
    document.write(a.toExponential() + "<br>"); //shows as many digit it needs after decimal point -> 5.8975998745e+4
    document.write(a.toExponential(2) + "<br>"); //show only two digit after decimal point -> 5.90e+4
    document.write(a.toExponential(4) + "<br>"); //show only four digit after decimal point -> 5.8976e+4













    //The toFixed() method converts a number into a string, rounding to a specified number of decimals. if the desired number of decimals are higher than the actual number, zeros are added to create the desired decimal length.

    let a = 19.65823;

    document.write(a.toFixed() + "<br>"); //by default is 0 if no arguments are given. so rounds 19.65823 to 20 and 0 digits were added after decimal point
    document.write(a.toFixed(2) + "<br>"); // 2 digits were rounded after decimal point -> 19.66
    document.write(a.toFixed(4) + "<br>"); // 4 digits were rounded after decimal point -> 19.6582
    document.write(a.toFixed(8) + "<br>"); // 8 digits were rounded after decimal point -> 19.65823000. 3 zeros are added to create the desired decimal length
















    //The toPrecision() method formats a number to a specified length and change data type to string. A decimal point and nulls (null mean 0) are added (when needed), to create the specified length. The number of digits (argument), If omitted (leave out the argument), it returns the entire number (without any formatting)


    let a = 19.65823;
    document.write(a.toPrecision() + "<br>"); //no argument so it returned the entire number -> 19.65823
    document.write(a.toPrecision(2) + "<br>");//2 value to the parameter, so it returned 2 length number after round up -> 20
    document.write(a.toPrecision(4) + "<br>");//4 value to the parameter, so it returned 4 length number after round up -> 19.66
    document.write(a.toPrecision(9) + "<br>");//9 value to the parameter, so it returned 9 length number after round up. 2 extra nulls (0) are added to create the specified length. -> 19.6582300



















    // toInteger() method returns true if the value is number data type and an integer (not decimal). otherwise if decimal value or number value inside string, or any other data type returns false. An integer is a whole number (not a fraction) that can be positive, negative, or zero. Therefore, the numbers 10, 0, -25, and 5,148 are all integers


    document.write("no parameter: " + Number.isInteger() + "<br>"); //false
    document.write("100: " + Number.isInteger(100) + "<br>"); //true
    document.write("-100: " + Number.isInteger(-100) + "<br>"); //true
    document.write("200-100: " + Number.isInteger(200 - 100) + "<br>");//true
    document.write("100.45: " + Number.isInteger(100.45) + "<br>"); //false
    document.write("0.1: " + Number.isInteger(0.1) + "<br>"); //false
    document.write('"100": ' + Number.isInteger("100") + "<br>"); //false
    document.write("'hello': " + Number.isInteger("hello") + "<br>"); //false
















    /*
    isSafeInteger() method returns true  if the value is number data type and an safe integer (not decimal). otherwise if decimal value or number value inside string, or any other data type returns false. 
    
    JavaScript can only safely represent integers (not decimal) in the range from 2^53-1(9.0071993e+15) to -2^53-1(-9.0071993e+15) (means range from 0 to 9007199300000000). Byond this range, JavaScript integers are unsafe. Fractions and decimals are not integers, means decimal numbers are not safe integers. 
    */

    document.write("no parameter: " + Number.isSafeInteger() + "<br>"); //false
    document.write("100: " + Number.isSafeInteger(100) + "<br>"); //true
    document.write("-100: " + Number.isSafeInteger(-100) + "<br>"); //true
    document.write("200-100: " + Number.isSafeInteger(200 - 100) + "<br>");//true
    document.write("100.45: " + Number.isSafeInteger(100.45) + "<br>"); //false
    document.write("0.1: " + Number.isSafeInteger(0.1) + "<br>"); //false
    document.write('"100": ' + Number.isSafeInteger("100") + "<br>"); //false
    document.write("'hello': " + Number.isSafeInteger("hello") + "<br>"); //false
    document.write("'hello': " + Number.isSafeInteger(9007199300000001) + "<br>"); //false













    /*math object methods:
    the math object holds a set of constant and methods that enable more complex mathmetical operations than the basic arithmatic operators. we cannot initiate (create a new object with math object) a Math object. The Math object is static, so it's properties and methods are accessed directly.

    static methods are called without creating object, and cannot be call through a class instance (object). static methods are called via objectName.
    */









    // max() method. returns Number, representing the highest number of the arguments, or -Infinity if no arguments are given, or NaN if one or more arguments are not numbers or you give an array as argument

    // max method Returns the number with the highest value:
    var a = Math.max(0, 150, 30, 20, 38);

    document.write(a);

    document.write("<br>");

    //min() method. returns Number, representing the lowest number of the arguments, or Infinity if no arguments are given, or NaN if one or more arguments are not numbers or you give an array as argument

    // min method Return the number with the lowest value:
    var b = Math.min(0, 150, 30, 20, 38);

    document.write(b);










    /*The round() method rounds a number to the nearest integer, like we do in real life.

    If that digit is less than 5, do not change the rounding digit but drop all digits to the right of it.
    If that digit is greater than or equal to five, add one to the rounding digit and drop all digits to the right of it.

    ex: 2.49 will be rounded down (2), and 2.5 will be rounded up (3).
    */

    document.write(Math.round(2.1) + "<br>"); //2
    document.write(Math.round(6.4) + "<br>"); //6
    document.write(Math.round(6.5) + "<br>"); //7
    document.write(Math.round(6.6) + "<br>"); //7
    document.write(Math.round(0.4) + "<br>"); //0
    document.write(Math.round(0.5) + "<br>"); //1
    document.write(Math.round(-2.1) + "<br>"); //-2
    document.write(Math.round(-6.4) + "<br>"); //-6

    // some computer programs round -6.5 to -7, others (javascript) to -6.
    document.write(Math.round(-6.5) + "<br>"); //-6 
    document.write(Math.round(-6.6) + "<br>"); //-7










    /*The floor() method rounds a number DOWNWARDS to the nearest integer, and returns the result (downer integer). If the passed argument is an integer, the value will not be rounded. 
    */

    //round down value is 2
    document.write(Math.floor(2.1) + "<br>"); //2

    // round down method doesn't count the values of positive decimal after decimal point and doesnot increases 1 even where after decimal point value is equal or higher than 5
    document.write(Math.floor(6.65) + "<br>"); //6
    document.write(Math.floor(0.4) + "<br>"); //0

    // round up will be 1. but floor method does the round down, so returns 0
    document.write(Math.floor(0.6) + "<br>"); //0

    //bigger negative value is downer than smaller negative value. so floor method increases 1 to round down the negative numbers. floor method doesn't count the values of negative decimal after decimal point and increases 1 even where after decimal point value is 1
    document.write(Math.floor(-2.1) + "<br>"); //-3
    document.write(Math.floor(-6.65) + "<br>"); //-7













    /*The ceil() method rounds a number UPWARDS to the nearest integer, and returns the result (upper integer). If the passed argument is an integer, the value will not be rounded. 
    */

    //ceil method doesn't count the values of positive decimal after decimal point and increases 1 even where after decimal point value is 1
    document.write(Math.ceil(2.1) + "<br>"); //3


    document.write(Math.ceil(6.65) + "<br>"); //7
    document.write(Math.ceil(0.4) + "<br>"); //1
    document.write(Math.ceil(0.6) + "<br>"); //1

    // when negative round up value with decimal 6 or higher, the value will be increased by 1. but ceil method does the round up (not round down), so returns -2
    document.write(Math.ceil(-2.1) + "<br>"); //-2
    document.write(Math.ceil(-6.65) + "<br>"); //-6














    //The random() method returns a random number from 0 (inclusive) up to but not including 1 (exclusive).0


    //Math.random method returns rendom values starting from 0............ so i added 1, so the values will be shown starting from 1...... and multiplied the random number to 100. so the random method value range will be from 1.... to 100..... and used Math.floor method to round down that number into integer (without decimal).
    let a = Math.floor(Math.random() * 100 + 1);

    document.write(a);


</script>