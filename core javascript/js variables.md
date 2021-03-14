# js built in data types


## var (declaration, initialization, hoisting, scope):

<script>
    // native objects: str, number, boolean, function, date, object, array, math, regexp, error. and all global JavaScript objects, any functions constructor or factory (not class), and variables (not let and const) automatically become members of the window object. the window object is a global object. and javascript doesn't have tuple.

    //any var defined with var is global variable until it is inside a function. then it's local variable. and even inside function, any variable defined without var keyword will be global variable. and it is recommended to use less global var in javascript.

    var name;//declaring. variable declaration is hoisted with undefine initilized in javascript
    name = 'mess shahadat'//initializing / assigning

    var name; // redeclaring. without initialization will return the first initialized value


    name = 'mohammad yasin'//reinitializing / reassigning / overwriting

    //declaring multiple variable at the same time.
    var my_name = 'mess shahadat',
        my_age = 18,
        married = false;

    //you can format the code with multiple spaces or line breaks as you want, cause javascript will ignore those spaces. except for arrow function.
    document.write
        (
            'name: ' + name + '<br>'
        )//accessing variables value 

    document.write('my_name: ' + my_name + '<br>');
    document.write('my_age: ' + my_age + '<br>');
    document.write('married: ' + married + '<br>');









    //variable declared with let & const are block, statement or expression scoped and can't be redeclared. and can't declare let or const var that has been already defined by var. you can't access let & const variable before declaration. and if let & const var is defined inside function, loop, if or inside any other blocked statement. then it will be not be accessable outside of it's block. and inner function can access outer functions let & const variables. but outer function can't access inner functions any type of variable. and function expressions or Variables declared using the const and let (class also) do not become properties of global window object even when declared globally
    let a = "javascript";
    document.write(a +  '<br>');

    for (let i=0; i<2; i++){
        document.write (`${i} <br>`);
    }
        
    document.write(i);//can't access local statement variables
    




    // while the var declarations are initialized with undefined at the top , but let and const declarations remain uninitialized at the top. so even if let and const declaration are hoisted, accessing let and const before it's declaration will give error. for this reason let and const hoisting are not valid (including for class also ). cause these variables are not accessible before there actual declaration.
    let a;
    document.write(a); //returns undefine
    a = 10;





    
    //const is immutable variable that have scope like let variable but you can't reassign (change) it's value. and you must initialize this const variables value while declaring. even if you initiate const vars value with a variable, and overwrite that variable, the const var value will be same and will not be overwritten. cause you cannot reinitialize the const var.
    const b = "is immutable";
    document.write(b +  '<br>');


    var mango = "mango";
    let mang = mango;
    document.write(mang);

    mango = "orange";
    mang = mango; // if const, you cannot reinitialize the const value, so the value will be same
    document.write(mang);


</script>
