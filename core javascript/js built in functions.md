# javascript

## built in functions in javascript
## write(), alert(), prompt(), typeof():


<script>

    //document.write (The write() method writes HTML expressions or JavaScript code to a document.The write() method is mostly used for testing. If it is used after an HTML document is fully loaded, it will delete all existing HTML.)
    var name = 'mess';

    document.write('welcome '+ name)//to show content in the loaded html document
    




    //window.alert
    window.alert('welcome ' + name);//to show some data in browsers alert box. and alert box will freeze everything else that moment 
    



    //prompt
    var a = prompt('plz enter your name: ');//to show a input prompt to visitor and get some input.
    document.write(a);




    //xiaomi object
    xiaomi = {
        model : "argument",
        price : function() { return document.write(xiaomi.model + "price is 3000 only<br>")};
    }

    //hasOwnProperty. is a built in function. use this to check if a property exist in a object
    if (xiaomi.hasOwnProperty("model")){
        document.write("available");
    }else{
        document.write("not available");
    }







    //typeof()
    function mess(){} //declaring function

    let fun = function() {} // declaring function expression

    //to see what is the data type of it's operand (the operand is what you give it as parameter). type of returns every data type wrapped with quotes. means it show what type of data it is but shows in string
    document.write("<br>" + typeof(name)); //returns "string"
    document.write("<br>" + typeof(xiaomi)); //returns "object". array data type also returns object not array. null data type also returns object not null
    document.write("<br>" + typeof(mess)); //returns "function"
    document.write("<br>" + typeof(fun)); //returns "function"

    let a = typeof(xiaomi); //returns object wrapped with quotes
    document.write(typeof(a));// returns string of typeof(typeof(xiaomi))


    let mess = 22;

    // returns fasle (cause ether way it checks data type not value)
    if(typeof(mess) === "22"){
        document.write("true");
    }
    else{
        document.write("false");
    }






    //delete
    list = ["hello", 1,2,3,"mic testing"];
    
    document.write(list + "<br>");
        
    delete window.list;
    document.write(list + "<br>");

    /*
    The delete operator removes a property from an object or an item from an array. It cannot remove the whole variable or anything (function, object or array) that is declared using var, let or const. but if it's declared globally without var, let or const, you can delete the whole object from the global window object. ex: delete window.list; or You can set x = null or x = undefined to remove the reference of whole object, but can't delete the whole object with delete operator */

</script>

