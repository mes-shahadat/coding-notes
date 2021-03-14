# access dom elements


<!-- getElementById, getElementByTagName, getElementByClassName, method chain, querySelector, querySelectorAll, for loop -->

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <title>get element by id</title>
</head>

<body>

    <h1 class="mess">welcome to javascript</h1>

    <h1 class="myclass mess">you are learning advanced javascript</h1>

    <p id="mess">this is the first line
        <span class="myclass">i have leaved the python</span>
        <em>sry</em>
        <span>i have leaved the python</span>
    </p>

    <p id="p2">this is the second line</p>

    <div id="div">
        <p id="p3">this is the first line inside div</p>

        <p class="mess">this is the second line inside div</p>
    </div>


</body>

</html>






<script>        //document means javascript will search id from the whole document. only accepts single parameter
    var domdoc = document.getElementById("p2");//use get element by id to get the single object as html element. The getElementById() method returns the html element that has the ID attribute with the specified value. can't use document.body in getelementbyid method

    document.write(domdoc);

    console.log(domdoc);

</script>









<script>

    // You can use the length property of the HTMLCollection object to determine the number of elements with the specified tag name, then you can loop through all elements and extract the info you want.

    var domdoc1 = document.getElementsByTagName("p"); // The getElementsByTagName() method returns a collection of all elements (live node) in the document with the specified tag name, as an HTMLCollection object. can't use multiple tagname in this method

    var domdoc2 = document.body.getElementsByTagName("*"); // getelementsbytagname excepts single tag name parameter inside strings, and the parameter value "*" returns all elements from the document.body tags

    document.write(domdoc1);

    console.log(domdoc1); //The HTMLCollection object represents a collection of nodes (like an array). The nodes can be accessed by index numbers. The index starts at 0.

    console.log(domdoc2);

</script>












<script>

    var domdoc3 = document.getElementById("p1").getElementsByTagName("span");//you can be more spacific by selecting the node element first (first node element must be id) then selecting the tags you want.

    var domdoc4 = document.getElementById("p1").getElementsByTagName("*"); //currently it only shows all the inline block elements, ignoring block elements, but other browser may support it, thus this can be a problem. so, try to use "*" less

    document.write(domdoc3);

    console.log(domdoc3);

    console.log(domdoc4);

</script>














<script>

    var data = document.getElementsByTagName("p"); //this way you can get both node list and length separately

    var dataLen = data.length; //The length property returns the number of nodes in a NodeList object.This property is read-only.

    var len = document.getElementsByTagName("p").length;//get length in one line

    document.write(dataLen);

    console.log(dataLen);

    console.log(len);

</script>


















<script>

    var p1 = document.getElementsByTagName("p")[0];//to access the single (indivisual) node element at 0 index from the node list.

    console.log(p1);

    var data = document.getElementsByTagName("p"); //this way you can get both node list and length separately

    var dataLen = data.length;

    for (let i = 0; i < dataLen; i++) {
        document.write(document.getElementsByTagName("p")[i] + "<br>");
        console.log(document.getElementsByTagName("p")[i]) + "<br>";
    }


</script>

















<script>


    var result = document.getElementsByClassName("mess");//The getElementsByClassName() method returns a collection of all elements in the document with the specified class name, as an HTMLCollection object. The HTMLCollection object represents a collection of nodes. The nodes can be accessed by index numbers. The index starts at 0.

    var result2 = document.getElementsByClassName("mess myclass");//Get all elements with both the "mess" and "myclass" classes

    console.log(result);

    console.log(result2);


</script>
















<script>

    //more specificly accessing a single element (first node element must be id) by using getElement method is called method chain.
    var result = document.getElementById("div1").getElementsByClassName("mess");

    console.log(result);

</script>
















<script>

    //length property in getElementByClassName method.
    var len = document.getElementsByClassName("mess").length;

    console.log(len);

</script>














<script>

    //for loop in getElementByClassName method.
    var len = document.getElementsByClassName("mess").length;

    for (let i = 0; i < len; i++) {
        console.log(document.getElementsByClassName("mess")[i]);
    }

</script>
















<script>
    /*
    dom query selector (means you can use css selectors to access single node element, use query selectors to get the first single element & use getElement methods to get specific elements. and some browser do not support query selector):
    
    The querySelector() method only returns the first element (single element) that matches the specified selectors (returns null if no matches found). To return all the matches, use the querySelectorAll() method instead.

    querySelector returns object htmlelement.
    */

    //element selector returns the first element that matches a specified CSS element selector in the document.
    var elsec = document.querySelector("p, h1"); //returns h1 element cause it found the h1 element first

    console.log(elsec);

    //id selector returns the first element that matches a specified CSS id selector in the document.
    var idsec = document.querySelector("#p3,#p2"); //returns p2 element cause it found the p2 id element first

    console.log(idsec);

    //class selector returns the first element that matches a specified CSS class selector in the document. you can be more specific like in css. ex: p.mess
    var clssec = document.querySelector(".mess, .myclass"); //returns h1 element cause it found the h2 class element first

    console.log(clssec);

</script>


















<script>
    /*
    The querySelectorAll() method returns all elements in the document that matches a specified CSS selector(s), as a static NodeList (not live nodelist) object.

    getElement methods returns object htmlcollection (collection of HTML elements) -> which do not contain attribute nodes and text nodes.
    querySelectorAll returns object nodelist (collection of document nodes) -> which contain attribute nodes and text nodes.
    */

    //element selector
    var elsecall = document.querySelectorAll('h1, p, #p2');//returns nodelist of all h1 and p and id #p2 elements.

    console.log(elsecall);

    //id selector
    var idsecall = document.querySelectorAll('#div');//returns nodelist of all elements who has #div id.

    console.log(elsecall);

    //class selector
    var clsecall = document.querySelectorAll('.mess, .myclass');//returns nodelist of all elements who has mess or myclass class

    console.log(elsecall);

    //attribute selector
    var atsecall = document.querySelectorAll('p[class]');//returns nodelist of all p elements who has class attribute

    var atsecall2 = document.querySelectorAll('p[id=p3]');//returns nodelist of all p elements who has id attribute = p3

    console.log(atsecall);

    console.log(atsecall2);

</script>





















<script>

    var result = document.getElementById("mess").querySelectorAll("span.myclass");//more specific with method chain
    //or
    var result1 = document.querySelectorAll("#mess span.myclass");// more specific with queryselectorall

    document.write(result1);

    console.log(result1);

</script>



















<script>

    //length method in query selector
    var len = document.querySelectorAll(".mess").length;

    document.write(len);

    console.log(len);

</script>














<script>

    //loop in queryselector nodelist
    var data = document.querySelectorAll(".mess");

    var len = data.length;

    for (let i = 0; i < len; i++) {
        console.log(data[i]);
    }

</script>