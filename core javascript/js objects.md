# js objects


## object (object literal, adding (properties, methods), accessing, deleting, overwriting, factory function, constructor, hasOwnProperty, for in loop)
<script>
    /* type of objects: 
    user define object: custom object that are created by the programmer
    native objects: str, number, boolean, function, date, object, array, math, regexp, error
    host object, document object */





    //Object literals means encapsulated (scoped) data. object literal is a comma-separated list of name-value pairs wrapped in {}. array literal is a comma-separated list wrapped in []. there is also template literals(string literals), which is string wraped with backtick (`), and it's different that array or object literals.
    var mess = {
        list: [10, "20", true], // array literals
        dict: { x: 40, y: 30 }, // nested object literals
        fees: {} //created empty object using object literal
    } //declared and initialized an single object at the same time using object literales








    let extra = 5;

    /* an object is collection of properties and methods. property means (name :value) kay : value pairs. and a property value can also be a function. in that case this function will be called as that objects method not as property. 
    
    As we already know, a variable cannot have a name equal to one of language-reserved words like “for”, “let”, “return” etc. But for an object property, there’s no such restriction: In short, there are no limitations on property names. They can be any strings or symbols (numaric). and object name which are string or Other types are automatically converted to strings. For instance, a number 0 becomes a string "0" when used as a property key. */

    //creating single object using object literals by declaring and initializing object at the same time
    var schoolfees = {
        //rahul and other properties are member of fees object
        //key: value
        rahul: 100,//property (key : value). typeof is number
        "sumit sha": 200,//seprate every members by comma.
        total: function () { return (100 + 200); }//method (key: function). typeof is function

        //accessing own property
        rprice: function () { return (this.rahul + extra); }// this.rahul (schoolfess.rahul) means the rahul is property of this (it's own) object. in other words this keyword tell's javascript to look for the property from this (it's own) object not from any variable outside of object. inside object's method this refers to the owner object. remember if a method (function) returns another function, than inside that function you can't access object properties with "this" keyword. cause that function is regular function and inside regular function this refers to window object.
    };










    //declaring an single empty object using object literal. it is also hoisted in javascript
    let fees = {};



    //initializing / adding single new property to fees objects. you can add property to an existing object from anywhere in javascript
    fees.shahadat = 100; // you can add single word name property to your object with . operator.
    fees["mohammad yasin"] = 350; // you need to use [] operator to add two word named property with space between.







    //accessing single property of an objects using (. or []) operator. use for in loop to access multiple properties
    document.write(fees.shahadat); // accessing objects property with . operator
    document.write("<br>");
    document.write(fees['mohammad yasin']);// with . operator you can't access objects property which has two word name with space between.
    document.write("<br>");

    //accessing single method of an object using object literal.
    document.write(schoolfees.total())// invoking / calling method (key: function) with . operator. if your method has two word name with space then call method with [] operator. ex: schoolfees['total']()
    document.write("<br>");




    //deleting single propertys or method of an object using delete operator. (can't delete whole object using delete operator)
    document.write(fees.shahadat); //before deleting. you can use or access that object property

    delete fees.shahadat; //deleting object property with delete operator.
    document.write("<br>");

    document.write(fees.shahadat + " // deleted value"); //after deleting. you can't use or access that object property
    console.log(fees);
    document.write("<br>");









    //object constructor. adding, accessing and deleting property is same as object literals. ignore this method to create single objects, use object literals to create single object
    let hello = new Object(); //Object() is an object constructor; new object(); new operator creates an single empty object using object constructor. you can also initialize it while declaring. let hello = new Object(); is equivalent to let hello = {};

    hello.antor = 350; //adding properties to the empty object
    hello["mohammad yasin"] = 150;
    hello.total = function () { return (350 + 150); }

    hello['shei tumi'] = [110, 12, 23];//adding array to hello object with [] operator
    console.log(hello); // shows / logs hello object in chromes console.












    //factory function with parameter (this is hoisted in js). when a function returns an object (that has all needed methods attached to it as normal properties, not an empty object). it is called as factory function. you can create as many as objects you want from a single factory function
    function mobile(model_no) {
        return { //returns object
            model: model_no,// defining property. use coma to seprate every member from factory function
            price: function () { return "price is 3000 only"; } //defining method
        };
    }
    //(syntax: const objectname = factoryfunc("argument")) //doesn't need to use new operator
    const samsung = mobile("samsung A30"); //creating object from factory function like this is called as creating object instance from factory function (Usually an instance will have values assigned to it's properties that differentiates it from other instances of the type of object. (instance = copies)) 

    /* now the samsung variable contains / returns this object. 
        means const samsung = mobile("samsung A30"); 
        =
        samsung = {
            model : "samsung A30",
            color : "white" ,
            price : function () { return "price is 3000 only" ;}
        }
    }*/

    document.write(samsung.model + " " + samsung.price()); //to access object properties and method you need to access it with the object instance







    //ES6 eliminates the duplication when an object property is the same as the name of a local variable. use this short hand when you create object using object literals or factory function. do not use with constructor or class.
    function user(fName, lName) {
        return {
            //fname : fname == fname
            fName,
            lName,

            //fullname : function() {return ("statements")}; == fullname() {return ("statements")} //new in es6
            fullName() {
                return this.fName + " " + this.lName;
            }
        }
    }
    let yasin = user("mohammad", "yasin");
    document.write(yasin.fullName());











    //you cannot directly call constructor or class in javascript, use new operator to create object instance with them.
    // constructor. use pascal casing to write constructor's name. constructor are hoisted in javascript. constructor is a special kind of function (who initialize a object or you can say add properties and methods to a object). you can use it to make as many as objects you want with different properties value from a single constructor function. (you can also call this class instead of constructor)
    function Mobile(mobileModel) {
        this.model = mobileModel; //use semicolon (;) to separate every member of constructor
        this.color = "white"; //adding color property to this (means to the current empty object)
        this.price = function () { return document.write(this.model + "price is 3000 only<br>") }; //adding price method to this property
        console.log(this);//inside object's method this refers to the owner object
    }
    const xiaomi = new Mobile("redmi note 7 pro "); //creating new xiaomi empty object and initializing object from constructor. creating object from class like this is called as creating object instance from class object (creating class instance). if you call a function or constructor with new operator than in that function "this" keyword refers to the object you create with new operator.
    
    xiaomi.model; //access object's property 
    xiaomi.price(); //calling object's price method

    /* const xiaomi = new constructorName("arguments"); creates an  empty object like this -> const xiaomi = {} and passes that empty object to the constructor's this keyword. then the constructor adds the predefined properties to this keyword (curren object). and after, the new constructorName() method creates __proto__ for the object instance (sets the created object prototype as constructor prototype)


    const xiaomi = new constructorName("arguments"); //new operator creates an empty object like below
    const xiaomi = {}; // new operator then creates proto of constructor and send the created object (xiaomi) with other parameter to constructor. inside constructor "this" parameter gets changes with object name like below.

    function Mobile(mobileModel){
        xiaomi.model = mobileModel; //constructor adds the properties to the current empty object (adding property to this keyword)
        xiaomi.color = "white" ;
        xiaomi.price = function() { return document.write(xiaomi.model + "price is 3000 only<br>")};
    }

    //hence we get this object
    xiaomi = {
        model : "redmi note 7 pro",
        color : "white",
        price : function() { return document.write(xiaomi.model + "price is 3000 only<br>")};
    }
    */

    /* in javascript "this" keyword refers to the object it belongs to. inside object's method "this" refers to the owner object. while alone or inside a regular function "this" refers to the global windows object*/
















    //creating class using custom construction with function expression in javascript. classes are faster than factory function
    let mobile = function (modelNo, mPrice) {
        this.model = modelNo; //every member created inside constructor are called instance member. and you can also  call instance property or method but don't call them prototype property or method (instead of instance) if there are defined with prototype.
        this.color = "white";//any property created inside constructor with "this" keyword is called public property
        var sellingPrice = mPrice; //any property defined with var, let or const is private property of constructor, and can be access inside constructor only. can't declare private member inside any object created by object literals.
        var sprice = function () { return document.write("selling price is: " + sellingPrice) }; // this is private method
        this.sellingPrice2 = function () { return sellingPrice };//this public method returns the private property (which is read only)
    }
    let nokia = new mobile("nokia e62", 5000);
    document.write(nokia.sellingPrice2());//reading private property indirectly. therefore can't make any modifications to the real private property like reassigning the mobile price.

    //syntax: className.prototype.propertyName = value; creating prototype member.
    mobile.prototype.ram = "4gb";//adding prototype member (property) to a class. any object created by mobile class will also have this ram property
    console.log(nokia);//shows object in chromes console

    /*
    you can add property and methods to class (constructor) using it's prototype. prototype means parent class (super class) of class (meaning All JavaScript objects inherit properties and methods from a prototype). any member created by prototype is called prototype member. generally prototype is used to add methods to an class. if object doesn't find it's property inside class (instance member) then it tries to access those properties from the clasess prototype (cause object instance does not has prototype, but has __proto__ which point to the constructor / class prototype).
    */




    //prototype theory --> geeky show (core javascript video from 83 - 87)




    //hasOwnProperty. is a built in function. use this to check if a property exist in a object
    if (xiaomi.hasOwnProperty("model")) {
        document.write("available");
    } else {
        document.write("not available");
    }














    //for in loop to access all properties at once. for..in loop iterates over all property keys (returns keys) not values.the for in loop is used to loop through an objects properties (on both instance member and prototype member). and inside for in loop you can't access objects properties with . operator. you need to use [] operator to access objects properties
    // Note: Do not use the for/in statement to loop through arrays where index order is important. Use the for statement instead.
    for (let key in xiaomi) { //syntex is for ( var variableName in objectName)
        if (typeof xiaomi[key] !== 'function') { // if object key type is not function executes the code below
            document.write(key + " : " + xiaomi[key] + "<br>");//shows key : value of objects 
        };
    }

    /*
    typeof key = "string".
    typeof xiaomi[key] means:
    typeof (xiaomi["model"]) //returns "string"
    typeof (xiaomi["color"]) //returns "string"
    typeof (xiaomi["price"]) //returns "function" ("function" !== "function" -> same value and same data type returns false)

    xiaomi = {
        model : "redmi note 7 pro",
        color : "white",
        price : function() { return document.write(xiaomi.model + "price is 3000 only<br>")};
    }
    
    
    //also looping using object.key will return all the instance members key ignoring  prototype members key
    document.write(object.keys(xiaomi));
    */





</script>