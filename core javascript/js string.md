# js string



## string (string constructor, declare, initialize, arithmatic operators with string, escape sequence, template literals, tagged template literals, length property)

## string methods: (charAt(index), charCodeAt(index), uppercase, lowercase, trim():rm spaces, replace(val, rval), split():str to arr, indexOf(val, index), -> search(val), slice(findex,lindex), -> subString(findex,lindex), -> subStr(findex, charcount) )


<script>
    //string is built in object corresponding to the primitive string data type. string is group of characters.



    //assign string data type to a variable using primitive datatype. string variable created via primitive data type returns typeof to string. javascript doesn't count (ignores) multiple spaces in string (use \0). and you can't write single slash (\) inside string (use \\). you can't use multiline (use \n). you can't use both single and double quote inside string (use \' and \"). you can't use tab space inside string (use \t escape notation).
    let var1 = 'to'; //you can say you are declaring var using string literals
    let str1 = "welcome 'to' javascript";//use double quote (") to create string if you want to use single quote (') inside 
    let str2 = 'welcome "to" javascript';//use single quote (') to create string if you want to use double quote (") inside 
    let str3 = `welcome ${var1} javascript`;//use backtick (`) to create string if you want to use javascript expressions or double or single quote inside without escape notation. using backtick (`) instead of quotes to create stirng is called template literals




    document.write(str3 + "<br>");//accessing string variable
    document.write(typeof (str1) + "<br>");





    //assign string data type to a variable using String constructor. string variable created via string constructor returns typeof to object. and string constructor is slower than string literals
    let str4 = new String("welcome to javascript");
    document.write(str4 + "<br>");
    document.write(typeof (str4) + "<br>");







    //concatenation on string
    let str5 = "welcome";
    let str6 = "javascript";

    let str7 = str5 + " to " + str6;//concating variable and string using + (plus operator)
    document.write(str7 + "<br>");

    let str8 = str5.concat(" to ", str6);//concating variable and string using built in concat method. you can check built in method in the objects proto. console.log(str5.__proto__);
    document.write(str8 + "<br>");






    /*
        escape notations / sequence:
        \0 - the null character (space) ex: "iam\0good\0boy"
        \' - single quote (single quote) ex: iam \'good\' boy
        \" - double quote (double quote) ex: iam \"good\" boy
        \\ - backslash (single backshlash) ex: D:\\okayish-cabinet
        \n - new line (another line) 1: 1st line \n2: second line
        \r - carriage return (ignore)
        \v - vertical tab (ignore)
        \t - tab (  ) ex: "iam good \tboy"
        \b - backspace (ignore)
        \f - from feed (ignore)
    */

    console.log("iam\0good\0boy");//document.write ignores spaces even after \t escape sequence. cause html also ignores spaces, and write method converts javascript \t to spacess. so use console.log









    //template literals are string literals allowing embeded expressions. you can use multiline string and string interpolation features with them. template literals are enclosed by the (`) character.

    let str = `hello
        world `;//with template literals you can use single quote or double quotes or multiline spaces inside string without escape sequence. docuement.write ignores multiline spaces (cause html ignore multiline spaces) use console.log

    let str2 = "welcome";

    let str3 = `${str2} to javascript`; //in template literals, string interpolation feature allows injecting variables, function calls, arithmetic expressions directly into a string by writing the var or function or arithmatic expression inside dollar curly braces ${expression}. you don't need to use + operator or concat method to concat and show variable with string
    console.log(str3);










    //tagged template literals

    //there are 5 movie tickets each is 200 tk. and you have buyed 5 tickets. you will get discount of 50 tk per each ticket you buy

    let movieTickets = 5;
    let ticketPrice = 200;
    let buyingTicket = 5;
    let ticketDiscount = 50;


    //tagged function. 1st parameter saves all the strings as array. other parameters will save one expression each. you can also use rest parameter which will save all the expression into an array.
    function ticket(allStrings, mvtkt, tktprc, buytkt, tktdis) {
        // return all statement wraped with backtick (`);
        if (buytkt < 5) {
            tktdis = 0;
            return `${allStrings[0]} ${mvtkt} ${allStrings[1]} ${tktprc} ${allStrings[2]} ${buytkt} ${allStrings[3]} ${tktdis} ${allStrings[4]}`
        }
        else {
            tkdis = 50;
            return `${allStrings[0]} ${mvtkt} ${allStrings[1]} ${tktprc} ${allStrings[2]} ${buytkt} ${allStrings[3]} ${tktdis} ${allStrings[4]}`
        }
    }

    //you need to write the tagged function name without () in order to call the tagged function. tagged function will store all the string values to the first parameter as array and all the expression in it's other parameters.
    document.write(ticket`there are ${movieTickets} movie tickets each is ${ticketPrice} tk. and you have buyed ${buyingTicket} tickets. you will get discount of ${ticketDiscount} tk per each ticket you buy`);











    //length property in string returns the length of characters in a string (it counts every character including spaces)
    let str = "welcome to javascript";

    document.write(str.length);










    //string methods:

    //charAt method returns the character (single letter) of an string from an specified position (index number)
    let str = "welcome to javascript";// string index numbers also starts from 0

    document.write(str.charAt(11));








    //charCodeAt method returns the unicode character (unicode letter) of an specified position (index) from a string 
    let str = "welcome to javascript";// string index numbers also starts from 0

    document.write(str.charCodeAt(11));








    //uppercase and lowercase method
    let str = "welcome to javascript";

    document.write(str.toUpperCase());//converts all strings to UPPER case. this doesn't modifies the orignal variable.
    document.write("<br>");
    document.write(str.toLowerCase());//converts all strings to lower case. this doesn't modifies the orignal variable. 









    //trim method removes white spaces from both side of a string. not from in between (middle). and this method doesn't changes the orignal variable.
    let str = "                welcome to javascript              ";//document.write will ignore whitespacess, so console log it.

    console.log(str.trim());








    /* replace() method. replaces a single specified value (only the first occurence) with another value in a string.
        syntax: replace("old", "new"); this method doesn't make changes to the orignal variable
    */
    let str = "welcome to javascript";

    document.write(str.replace("script", " programming"));








    /* The split() method is used to split a string into an array, and returns the new array. the string method separates strings according to a delimiter passed as it's first argument. Second argument is used to control the maximum number of substrings generated by splitting a string. this method doesn't modifies the origanl variable 
    
    syntax: str.split("delimiter", lengthNumber(optional))
    */
    let str = "welcome to javascript";

    document.write(str.split(" "));//Delimiter is a blank space, comma, or other character or symbol that indicates the beginning or end of a character string, word, or data item







    /* indexOf method is same as arrays indexOf method. indexOf method. returns the position of an specified character or word from an string. and the arguments are case sensetive. and you can't use regular expression in this method.
        if the item is not found then returns -1,
        if you don't specify the start position then the search will start from 0 index to the last index,
        if the item is present more than once the indexOf method will return the first items position
        syntax: var anyname = strVarName.indexOf(word, startPosition) 
    */
    let str = "welcome to javascript";

    let str1 = str.indexOf("co");//returns 3 (index of c is 3)

    let str1 = str.indexOf("cr");//returns 16 (index of c is 16)

    document.write(str.indexOf("a", 13));//starts searching from index 13 position






    /* the search method take a single argument and searches for the position of that argument from an string, and returns the position of the first matched argument. you can also use regular expression in this method.*/

    let str = "welcome to javascript";

    document.write(str.search("a"));//12





    /*  The slice() method copies the string starting from the start argument, and ends exactly right before the end argument, and returns the new values. this method can accept negative index. and it doesn't modifies the orignal variable.*/

    let str = "welcome to javascript";

    document.write(str.slice(11, 21));//21 is not included








    /*  The subString() method is same as slice method, but it cannot accept negative index*/

    let str = "welcome to javascript";

    document.write(str.substring(11, 21));//21 is not included








    
    /* The substr() method extracts parts of a string, beginning from the 1st argument and ending at the specified character count, and returns the specified number of characters. you can also use negative index. The substr() method does not change the original string.
    syntax: str.substr(startIndexNumber, characterCount);
    */

    let str = "welcome to javascript";

    document.write(str.substr(11, 10));//starting from 11 index copies and returns 10 characters.
</script>