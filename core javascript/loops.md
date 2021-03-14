# loops

## for loop:

<script>
    // for (first initialization; ---> test condition; ---> increament or decrement;). initialization is checked for only the first time. if test condition is true then runs the code statements. then increament or decreament is done

    // for loop for when you need to execute some codes for fixed number of times
    for (let i = 0; i < 5; i++) { // separated via semicolon, i++ increase i = 0; value by 1 untill i < 5; condition gets false.
        document.write(i + "<br>");
    }

    // nested for loop (for loop inside for loop)
    for (let i = 0; i<3; i++){ //outer for loop
        document.write('outer for loop executed ' + i + '<br>');
        for (j = 0; j<3; j++){ //inner for loop
            document.write('inner for loop ' + j + "<br>");
        }
    }
</script>




## note: understanding of array and object is needed. and for each in loop is depreciated in modern javascript 
## for in loop ( iteration / iterating / iterate), forEach loop, for of loop (iterator, iterables):

<script>
    /* 
    technical terms:

    iterating: iterating means looping in technical terms (Iteration is when the same procedure is repeated multiple times). you can also say traversing (which means "move through" or "iterate through") instead of iteration

    iterable: any iterable objects that are iterable by for of loop are called iterables (iterable object). Built-in iterables (iterable objects) are: String, Array, TypedArray, Map, and Set. An iterable object is any object that by default returns a function / method that produces an Iterator (function) for its Symbol (in other words iterable object has a built in method called iterator). for of loop uses iterator(function) for iteration in iterable object.

    technical explaination of iterable: an iterable object has an built method called symbol.iterator in it's property (by default in built in iterable objects). when this method is called by accessing it with that object (list[symbol.iterator]()) it returns a new iterator for the object. and for of loop uses next() method in that iterator to iterate the values of that object.

    iterator: Iterator always uses the best possible way to iterate through elements of the given collection, because the collection itself has its own Iterator implementation (methods for iterator).
     */



    //Both for..of and for..in statements iterate over lists; the values iterated on are different. and "iterating" is the technical term for looping.
    let list = [4, 5, 6];
    list.foo = "hello"

    // for..in iterates over all enumerable / assigned property keys(returns index number if only values are available.) of an object. the for in loop is used (created) for to loop through an objects property. and Destructuring inside for...in is deprecated. Use for...of instead.
    for (let key in list) {
        console.log(key); // "0", "1", "2", foo (for..in returns a list of keys from the object (any object) it's being iterated.)
    }//if you don't write let (let key in list) in condition then key will initialized as global variable. let key is empty variable which stores the key one by one overwriting other. you can write key or any other variable name.
    






    //for each loop is an method of array. it is depreaciated in javascript (means low amount of browser support it), and it is slower then other javascript loops. it loops through every element of an array and can return each value ( element) and index number and the whole array object also. it can also loop though collections like HTMLCollection and NodeList.

    //you can give any parameter name you like. i have written (value,index, array). you can skip the index and array in function argument but you need to write one parameter for the value. and the 1st parameter will be the value. and 2nd parameter will be index and 3rd parameter will be whole array object
    list.forEach(function(cvalue, cindex, arrobj){
        document.write(value + "<br>");
    })






    /* for..of iterates over the values of an iterable object. Therefore, you cannot use for…of loop to iterate on a uniterable object like number. Built-in iterables (iterable objects) are: String, Array, TypedArray, Map, and Set. and any other types like Objects are not iterable by for of loop (by default) unless they implement the iterable protocol for that object. and it supports all kinds of control flow in the loop body, like continue, break, return, yield and await. */
    for (let val of list) {
        console.log(val); // "4", "5", "6" (for-of loop iterates only over Iterable object. Any iterable object has an iterator. and when the iterator is called (while iterating / looping). it returns the objects value )
    }//if you don't write let (let val of list) in condition then val will declared as global variable.
</script>








## while loop, do while loop:

<script>
    //while loop first checks condition then keeps repeating an action until that associated condition returns false
    let i = 0;
    while (true) {//while loop is always true
        if (i == 3) { break; }//if this condition gets true it will break the loop 
        document.write(i + "<br>");
        i++
    }
    document.write(i);

    //nested while loop
    let i = 0;
    while (i < 3){ //outer loop
        document.write('<strong> this is outer loop </strong> ' + i + "<br>");
        i ++
        let j = 0;
        while (j < 3){ //inner loop
            document.write('this is inner loop ' + j + "<br>");
            j++
        }
    }














    //do while loop checks the condition after the code is executed. so the code gets executed atleast one time
    let i = 0;
    do {
        document.write(i + "<br>");
        i++;
        if (i == 3) { break; }
    } while (true)

    //nested do while loop
    let i = 0;
    do{ //outer loop
        document.write('<strong> outer do while loop </strong>' + i + "<br>");
        i ++;
        let j = 0;
        do{ //inner loop
            document.write('inner do while loop ' + j + "<br>");
            j++
        }while (j <3);
    } while (i < 3);
</script>
