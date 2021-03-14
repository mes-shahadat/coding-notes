# js class


## class (declaration, unnamed class expression, inheritence, predefined super method, static method)


<script>


    //custom class declaration. use pascal casing to write class name. class is not hoisted in javascript.
    class Mobile {
        //overwriting default constructor. and one class can only have one constructor
        constructor(modelNo) {
            this.mdl = modelNo;//instance member
            var price = 25000; //private property
            this.price2 = function () { return (price) };//to access private member write without "this" keyword
        }
        //defing method (don't use "this" keyword to create prototype properties or methods)
        display() { return ("model: " + this.mdl + "<br>price: " + this.price2()) };//prototype member
    }
    let samsung = new Mobile("samsung A30");
    document.write(samsung.display());











    //unnamed class expression. class is not hoisted in javascript. so you can't access object created by class before declaring that class.
    let Mob = class {
        constructor() {
            this.model = "redmi 7";
        }
    };
    let xiaomi = new Mob();
    document.write(xiaomi.model);














    // inheritence:

    //The extends keyword is used to create a child class of another class (parent). The child class inherits all the methods and properties (instance member and prototype member) of that class. A class that is derived (extended) from another class is called a subclass (derived class, extended class, or child class)
    class Father {
        //if parent class do not have constructor then it will get a default empty constructor
        constructor() {
            this.hardwork = 'really hard work';
        }
        showFMoney() {
            return "Father's Money <br>"
        };
    }


    //syntax: class subclass extends superclass{}. any class that extends superclass is called subclass.
    class Son extends Father {
        // if you don't define a constructor inside subclass it will inherit the parent class constructor.
        //any object create by son class can access all methods and properties of father class. cause son class has extended (inherit) father class. so son class can access properties and methods of father class. this is called single level inheritence.
        showSMoney() {
            return "Son's Money <br>"
        };
    }


    //extends means inherite. we use inheritence to inherite common properties and methods from another class
    class GrandSon extends Son {
        //any object create by grandson class can access all methods and properties of son class and father class also. cause grand son class has extended (inherit) son class who has extended (inherit) father class. so grandson class can access both classes properties and methods. this is called multi level inheritence.
        showGMoney() {
            return "Grandson's Money <br>"
        };
    }

    let gs = new GrandSon();
    document.write(gs.showFMoney());
    document.write(gs.showSMoney());
    document.write(gs.showGMoney());
    document.write(gs.hardwork);
















    //super method:

    class Father {
        constructor(fmoney) { //this constructor needs a money argument
            this.fmoney = fmoney;
        }
        showFMoney() {
            return ("Father's Money: " + this.fmoney + "<br>");
        };
    }


    class Son extends Father {
        constructor(fmoney, smoney) {
            //if parent class and sub class has constructor then you must call super method inside sub class constructor before adding any properties to sub class constructor, else will give error. super method is used for sending parameter to parent class constructor.
            super(fmoney);
            this.smoney = smoney
        }
        showSMoney() {
            return ("Son's Money: " + this.smoney + " <br>");
        };
    }


    class GrandSon extends Son {
        //in sub class same method name with differrent implementation will override the parent class method 
        showSMoney() {
            return "Grandson's Money <br>"
        }; //method overriding / redefining.
    }

    //object of son class
    let s = new Son(10000, 1000);


    document.write(s.showFMoney());
    document.write(s.showSMoney());


    //object of grandson class
    let gs = new GrandSon();
    document.write(gs.showSMoney());














    //static methods
    class Mobile {
        constructor (){
            this.example = "this is just an example";
        }
        //the static keyword is used to define a static method for a class. static methods are called without creating object, and cannot be call through a class instance (object). so you can't create static method or properties inside constructor. and We cannot directly access the instance properties within a static method because a static method can only access static properties or static methods with "this" keyword (and also can access arguments if has like normally). so it's properties and methods are accessed directly by className. static methods are often used to create utility functions for an application
        static property = "this is static property. cause it's outside of constructor";
        static disp() {
            return ("this is static method. means it is not accessible by object instance. instead by class" + this.property);
        };
    }

    let samsung = new Mobile;

    // document.write(samsung.disp());//can't access static method via this class instance. static methods are only accessible / callable via className
    document.write(Mobile.disp());

</script>