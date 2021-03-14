# js functions


## function (argument object, rest parameter, variable scope (hoisiting inside function), function hoisting), function expression, anonymous function, arrow function, IIFE function:

<script>


    //just defining function will not execute it's code by itself. you need to call the function where you need to execute the functions codes.

    // defining / creating / declaring function. 
    function display_name(var1, var2) {
        return (var1 + ' to ' + var2);// a return statement may return any type of data (object, array, variable, function) or expression. ex: document.write(var1);  to the caller.

        //return: The return statement stops the execution of a function and returns a value from that function to the caller.
        //statement : A statement is an instruction, an action. Remember conditions with if , loops with while and for — all those are statements, because they just perform actions and control actions, but don't become values. 
    }

    //invoking / calling the defined function
    display_name('welcome', 'javascript <br>');//it is possible to call a function before declaring it.








    //function execution
    var a = 10;
    document.write(a + "<br>"); //returns 10
    
    mess(); //function executes here where it has been called, calling before declaring function
    document.write(a + "<br>"); //returns 20
    
    //function is not executing here
    function mess(){ 
        a = 20;
    }
    document.write(a + "<br>"); //returns 20
    document.write(a + "<br>"); //returns 20

    /*
    mess(){ //function is executing here
        a = 20;
    }
    */


















    /*
    argument object. by default every argument is saved in a built in local scope object called arguments. you can use index on this arguments object to get the values, and can use the built in length method to get total argument item number. 
    
    // built in arguments object looks like this
    arguments = ["welcome", "javascript", "world", callee: ƒ, Symbol(Symbol.iterator): ƒ]//  the arguments object passed to a function is an Array-like object (not a real array) which has it's own arguments.length method, this is in order to retrieve the number of parameters passed to a function.
    */ 
    function disp(greetings) {
        arguments[0] = 'hello ';//overwriting 1st arguments object value means overwriting the 1st parameters value also.
        document.write(greetings);
        document.write(arguments[1]);
        document.write(arguments[2]);

        for (i = 0; i < arguments.length; i++) {//you can use length property in argument object to loop (even if it's not a real array it has it's own length property), and you can also use useless callee method (callee's only use is for argument objects) in this argument object. but you can't use array's method's cause it is not an array.
            document.write(arguments[i]);
        }
    }

    disp('welcome ', 'javascript ', 'world <br>');// javascript doesn't checks arguments data type and will not give any error, no matter how many argument you send or not send.









    //default parameters. are like local variables, thus you can't declare a let variable with same name as parameter
    function defparam(d1, d2 = [101, 420], d3 = null, d4) { // you can set str, int, boolean, array and null as default parameter. and any extra parameter without argument or without default value will get value of undefine, but will not give any errors. separate all the parameters by coma (,).
        document.write('d1: ' + d1 + "<br>");
        document.write('d2[1]: ' + d2[1] + "<br>");
        document.write('d3: ' + d3 + "<br>");
        document.write('d4: ' + d4 + "<br>");
    }

    defparam('javascript', [6251]);//if a parameter sets it's default as array with multiple element. and if you send single element to an array parameter as argument then accessing the other defaults from that array will return undefine.

    /*
    //array parameter
    function mess (arr=["hello",'to',"python", "programming"]) {
        document.write(arr[0] + "<br>");
        document.write(arr[1] + "<br>");
        document.write(arr[2] + "<br>");
        document.write(arr[3] + "<br>");
    }

    mess (["welcome"]);//if you only send one element to an array parameter then other array parameter will return undefine.
    */












    //rest parameter
    function toargs(a, ...args) { // any argument without any separate parameter for them will be stored in rest operator as an real array item (means wrapped with [] separated by coma). syntax is ...anyname. syntactically rest operator must be the last parameter in a function, else it will give syntax error. to get the data use index on the rest operator.
        document.write(a + "<br>");
        document.write(args + "<br>");
        document.write(args[1] + "<br>");
    }
    toargs(10, 20, 30, 40, 50);








    // ###############################################################################################################


    //variables scope in function. variable declared with var in functions are function scoped not block scoped.
    function locvar() {
        // you can't access functions local variable outside of funcitons scope. but in javascript if you define local variable inside a for loop or if statements block scope, you can access that local variable outside of loop or if conditions block scope. so, it is recommended to use let instead of var to create local variable. you can also overwrite global variable inside function by just reinitializing (not redeclare, cause you can't redeclare global variable inside function)
        var i = 'i is a local variable of outer function <br>'; //local var
        k = 'even if k is inside function scope. k is a global variable, cause it is not created with var'//global var
        document.write(i);
        function locvar2() {
            var j = "j is a local variable of inner function <br>";
            document.write(i);//inner function can access outer functions local variable, but outer function can't access inner functions local variable.
            document.write(j);
        }
        locvar2();
    }
    locvar();
    document.write(k);




    //variable hoisting inside function are scoped. local variables are also hoisted inside top of functions scope. you can access var variable before declaration but you can't access let & const variable before declaration.
    var a = "mess shahadat";

    function mess() {
        //any var declaration inside functions are hoisted here at top / begining of function. you can access global variable inside function. but you can't redeclare the var inside function. cause variable inside functions are scoped and redeclaring will only create a new local variable. however to overwrite the global variable inside function, you need to reinitialize the variable without declaring it with var keyword (a=10;). then it will overwrite global var but only after when the function is called. 
        document.write(a);
        document.write("<br>");
        var a = "mohammad yasin";

        mess = "mess"; //declaring global variable inside function (inside function just initializing any new variable without var or let keyword is called initializing a new global variable, and it can be accesses ouside of function)
    }
    mess();
    document.write(a);
    document.write(mess);//accessing functions global variable



    // variable hoisting inside if condition or in any loop condition are same (not scoped).
    if(true){
        //if, or any loop conditions block are not scoped in javascript. so you can redeclare and initialize global variable inside block. and will be overwritten outside of statement block after executing. and it can be accessed outside of statement blocks.
        var a = "abdur rahim";
        document.write(a);
        document.write("<br>");
    }
    document.write(a);
        document.write("<br>");




    //example of hoisted variable inside functions are not redeclarable
    const a = "mess shahadat";

    function mess() {
        //const is not redeclaring but declaring as a new local variable
        const a = "mohammad yasin";
        document.write(a);
        document.write("<br>");
    }
    mess();
    document.write(a);




    // ###################################################################################################################

    //function expression. creating function and asssigning that function to a variable is known as function expression
    var a = function mess(item1) {
        document.write('<br>' + item1 + ' iam an function expression');
    };//it is a good practice to end function expression with semi colon; function expressions are not hoisted in javascript.  you can also call function expression directly with () after curly braces before ending with semicolon.

    a('hello');











    //anonymouse function. a function without a name is called anonymouse function. and it also has it's own arguments object like other normal functions.
    var b = function () {
        document.write('<br> this is an anonymouse function <br>');
    }; //it is a good practice to end anonymouse function with semi colon; you can also call anonymous function directly with () after curly braces before ending with semicolon.
    b();









    //passing anonymous function as argument to a normal function
    function anonparam(anonfunc) {
        return anonfunc();//you need to call the anonymous function to execute anonymous functions codes
    }
    document.write(anonparam(function () { return "<br> hello iam anonymous function <br>" }));











    //returning anonymous function via normal function
    function retanon(a) {
        return function (b) { //returns anonymous function
            return (a + b);
        };
    }
    // document.write(retanon(10)(20));//short form
    var af = retanon(10); //calles and sends argument to retanon function and saves the return to af variable as variable expression
    document.write(af(20)); // calles and send argument to anonymous function









    //arrow function. you can also pass arrow function as argument or return an arrow function like anonymous function
    var arofun = a => a;// if you only return single statement then you can return that statement without {} and without return statement. and if you return single statement inside {} without the return statement, then it will return undefine value. arrow function don't have built in arguments object. and it is a good practice to end an arrow function with semi colon; arrow function is not hoisted in javascript.

    document.write('<br>' + arofun(20) + "<br>");












    // IIFE function, is a self executing anonymous function. where you write the whole anonymous function inside () and call that function via another () outside of () at the end and close it with a semi colon. don't write global variable inside IIFE function.
    (function (a, b) {
        document.write(a + b);
    })(10, 20);

</script>
