# js array

## array(declaring & initializing array, multidimensional array, adding(variable), overwriting, accessing, deleting array elements, array length property,, Array.isArray(), array constructor, for each loop, for loop, for of loop (iterable object) )

## array method (concat, slice, indexOf, join, reverse, fill, unshift, push, shift, pop, splice)


<script>
    //declaring and initializing 1D array using array literal. by default in array, index number count starts from index 0.
    let stu = ["mohammad yasin", "shakil", 'arif', 'joinal']; // instead of creating single variable for every item, array is a data item collection stored under single name thus it's easy to access.
    document.write(stu);
    document.write("<br>" + typeof (stu));//object




    let geek = [, , 69, "mess"];//you can also initialize unidefine / empty value in array with just coma
    document.write(geek[1]);
    document.write("<br>");


    //declaring empty array with array literals
    let students = [];

    //initialing value. you can't initialize any value to an array without any index number. if you want then you need to use push()method
    students[0] = "rahim";
    students[1] = "mohammad yasin";
    students[69] = "mess shahadat";// initializing "mess shahadat" in 69 index number of student array. it is better to initialize using serialize (in sequence) index number, not any random number like 69. cause that will create that many undefine (empty) element of that length.







    //overwriting / modifying single existing element
    students[0] = "antor das";//to modify an element you just need to reinitialize (initialize with the same index) the value



    //assigning an array to a variable will make that variable array (will not create a new array). means every elements of the array will also store in that variable with there index number. and modifying this variables value will also modify the orginal arrays value. (by default when you create variable and store another variable in it, then changing the main variables data do not changes the stored variables data but overwrites that variable)
    let mess = students;

    mess[1] = "abdur rahim";//overwriting value of students[1] indirectly







    //accessing single array element / item. you can access single array item with it's index number. means you need to know the index number of the element you want to access. and if you use an invalid index number (not initialized) then it will return undefine not error.
    document.write(students[1]);//you can also write index number inside quotes, you will not get any error for that. but it's not recommended.
    document.write("<br>");

    //accessing all items of students array
    document.write(students);
    document.write("<br>");

    //accessing all items of mess array
    document.write(mess);

    let a = 10, b = 20, c = 30;

    //you can also add initialize variable in array
    let varray = [a, b, c];

    document.write(varray[1]);






    //deleting single array element using delete operator. delete operator sets the element to undefine, so arrays length is not changed but the value is undefine (removed in a way). so accessing that element with that index number will return undefine (that item position will not be removed, and length will also include that undefine item as a item).
    delete students[69];//deleted element of students array at index of 69.
    document.write("<br>");
    document.write(students[69]);






    //length is a property of arrays not method. the length property retrieves the index number of the next available position from last element of array (in short returns total elements count). the length property gets automatically updated when new element are added to the array. for this reason length is commonly used to iterate through all elements of an array. syntax: array.length
    document.write(students.length);







    //array constructor. it is equivalent to array literal. means there is no difference between them. if you use array constructor to create array or use array literal to create array both are same. you can use any of both to create array.
    let consarray = new Array();// declaring single empty object using new operator with array constructor

    consarray[0] = "mohammad yasin";//adding a new value to consarray which is created by using array constructor

    document.write(consarray);

    //you can also declare and initialize array using array constructor
    let otherray = new Array(10); // don't use array constructor to create array if you only assign it a single numaric value. cause then it will not initialize the value but use it as the length of that array, and will give you many undefine values equal to that length.

















    //by default arrays index number starts from 0. so if you do itaration on array then you must initialize the i value to 0. else loop will ignore 1st element from the array.
    let looparray = ["mohammad yasin", "antor das", "stephen hawking", "elon musk"];

    //iteration with for loop in array.
    for (let i = 0; i < looparray.length; i++) {//separated by semicolon
        document.write(i + " : " + looparray[i] + "<br>");
    }






    //for each loop is an method of array. it is depreaciated in javascript (means low amount of browser support it), and this loop is really slower then other javascript loops. it loops through every element from array and can return each value and index number and the whole array object. it can also loop though  collections like HTMLCollection and NodeList.

    //you can write any variable name you like. i have written (value,index, array). you can skip the index and array in function argument but you need to write one variable for the value. and first argument will be the value.
    looparray.forEach(function (value, index, arr) {
        document.write(value + "<br>");
    })







    //for of loop. array is iterable object, so you can use for of loop to iterate over it's value
    for (let val of looparray) {
        document.write(val + "<br>");
    }











    //multidimensional arrays (arrays of array): you need to know number of rows in order to create multidimensional array.


    //declaring 2d empty array using object literal. geek = [row:[colum, colum, colum], row:[colum, colum, colum]]
    let geek = [[], []];




    //initializing 2d array
    geek[0][0] = "mess shahadat";
    geek[0][1] = "windows";
    geek[0][2] = 7;

    geek[1][0] = "antor das";
    geek[1][1] = "windows";
    geek[1][2] = 10;





    //accessing [0][1] = [0th row][1th colum]
    document.write(geek[0][1]);
    document.write("<br>");






    //declaring and initializing at the same time using object literal
    let mes = [
        ["abdur rahim", "windows", 7],
        ["mohammad zihad", "windows", 10]
    ];






    //declaring and initializing 2d array using array constructor
    let arrcons = new Array(
        ["mohammad yasin", "windows", 7],
        ["sagor", "windows", 10]
    );







    //accessing 2d arrays element using nested for loop
    for (i = 0; i < 2; i++) {//in outer for loop define row number in i
        for (j = 0; j < 3; j++) {//in inner for loop define colum number in i
            document.write(arrcons[i][j] + " ");
        }
        document.write("<br>");
    }









    //declaring 2d arrays with for loop
    let again = [];

    let row = 2;
    let colum = 3;






    //adding row to empty array using for loop
    for (let i = 0; i < row; i++) {
        again[i] = [];
    }




    //accessing / displaying rows and colums of 2d array
    for (let i = 0; i < row; i++) {
        for (let j = 0; j < colum; j++) {
            document.write(again[i][j] + " ");
        }
        document.write("<br>");
    }

















    //array methods:

    //concat method is an method of array. The concat() method is used to join two or more arrays. This method does not change the existing arrays, but returns a new array, containing the values of the joined arrays.

    //syntax: newArray = oldArray.concat(oldArray, oldarray or / and value1, value2); you can concat both arrays and values at the same time

    //declaring arrays
    let classC1 = ["mohammad yasin", "shohel mona", "rajib hossain", "cinmoy ghosh"];

    let classS = ["mohammad zihad", "antor das", "mohammad shihab", "mohammad arif", "shujoy ahmed"];

    let classS2 = ["showrob boiragi", "yasin arfat", "omi"];




    //concating / merging values to existing array and making an new array who has all values
    let classC2 = classC1.concat("showrob boiragi", "yasin arfat", "omi");

    document.write(classC2);
    document.write("<br>");





    //concating two existing array to another array who will have all the values of both arrays
    let classSC = classS.concat(classC1, classS2);// first the classS items will be show then classC1 items then classS2 items. in same sequence you have concatinated them.

    document.write(classSC);
    document.write("<br>");









    //array reverse method (reverses the orginial array sequence. means last element will become first element and vice versa)
    //The JavaScript array reverse() method changes the sequence of elements of the given array and returns the reverse sequence. This method makes the changes in the original array. so accessing the array later will return items in reverse
    document.write(classC1.reverse());
    document.write("<br>");









    //join method (use to change the default separator in a array). by default toString() method is called on every array and seprates every items with comma. you can use join method to overwrite it.
    //The join() method returns the array as a string. The elements will be separated by a specified separator. The default separator in array is comma (,). If the array has only one item, then that item will be returned without using the separator.
    //syntax: arrayName.join(separator);

    let newClassC1 = classC1.join(" => ");//creates new array from an old array and changes the default coma separator, but converts the array object to string object. doesn't changes the real array.
    document.write(newClassC1);//accessing newClassC1









    /*
    Array slice() Method returns the selected elements from an array, as a new array object. The slice() method selects the elements starting from the start argument, and ends exactly right before the end argument. and slicing an array doesn't modify the originial array.

    positive index: [0, 1, 2, 3, 4, 5]
    negative index: [-5, -4, -3, -2, -1] //negative index starts from 1 not from 0. negative indexes don't actually act like real indexes, cause you can't access array items with negative index. only use them with slice or splice method if you want
    
    syntax: arrayName.slice(begin_index_number, end_index_number);
    if staring index is undefine it will slice from 0 index
    if staring index is greater than the array length then will return empty array object.
    if ending index is undefine or greater than the array length then will slice untill the end index is finished
    */

    let newClassS = classS.slice(1, 4);//you can also give arguments in negative index
    document.write(newClassS);









    //Array.isArray returns boolean value if passed argument is array or not
    let list = [12, 34, 56, 78, 90];

    let check = Array.isArray(list);
    document.write(check);








    /*(usefull to add or remove element from the middle position of an array)
    splice method modifies the original array. (remove multiple elements from an original array and / or can add new elements in that array)
    
    syntax: arrayName.splice(startIndexNum, deleteCount, replaceValues). //if you have many replace elements separate it be coma.

    list.splice(2,0,"mess shahadat"); //splice method will start from index 2 position and delete 0 elements and will add values like mess shahadat starting from 2 position. you can also use negative index numbers in this method.
    */

    let geek = ["mohammad yasin", "mess shahadat", "ekon", "mohammad emon", "antor das"];

    geek.splice(2, 2, "abdur rahim", "mohammad zihad");

    document.write(geek);









    /*
    indexOf method. returns the position of an item from an array. the arguments are case sensetive.
    if the item is not found then returns -1,
    if you don't specify the start position then the search will start from 0 index to the last index,
    if the item is present more than once the indexOf method will return the first items position
    syntax: var anyname = arrayName.indexOf(itemName, startPosition);
    */

    let geek = ["mohammad yasin", "mess shahadat", "ekon", "mohammad emon", "antor das"];

    let position = geek.indexOf("Antor das", 1);//start searching from index 1
    document.write(position);









    /*
    fill method. modifies your orignal array and fill (replaces) all the element with static value starting from given starting position to ends exactly right before the end argument. if you don't specify the starting and ending position, it will fill (replace) all the elements with the given static value. it changes the orignal array.

    syntax: arrayName.fill(staticValue, startPosition, endPosition); ex: list.fill("don", 1,3);
    */

    let geek = ["mohammad yasin", "mess shahadat", "antor das", "abdur rahim"];
    geek.fill("Don", 1, 3); //doesn't include the last position. means ends exactly before the last position

    document.write(geek);






    //if you create array with array constructor and give it a single numaric value, that numaric value becomes length of that array
    let feek = new Array(3).fill("no value");//fill method with array object.
    document.write(feek);












    // unshift method can add multiple elements to the begining of any array (like reverse array). this method makes changes to the orignal array. syntax: arrayName.unshift(value1, value2, value3);

    let geek = ["mohammad yasin", "mess shahadat", "ekon", "mohammad emon", "antor das"];

    let newGeek = geek.unshift("abdur rahim", "mohammad zihad");//if you save the array with unshift method, it doesn't return the full array but returns the length of that array.
    document.write(geek + "<br>");
    document.write(newGeek + "<br>");











    // push method adds given arguments as elements to the end of an array. this method makes changes to the orignal array. just calling the orignal array will retrun the modified values. so you don't need to save the array.method to another variable to get the values. you can directly put the array.method inside document.write() or console.log() to get the full array.

    let geek = ["mohammad yasin", "mess shahadat", "ekon", "mohammad emon", "antor das"];

    let newGeek = geek.push("abdur rahim", "mohammad zihad");//if you save the array with push method to another variable, it doesn't return the full array but returns the total length of the original array.
    document.write(geek + "<br>");
    document.write(newGeek + "<br>");














    // shift method can remove single element from the begining of an array. it removes the first element of an array with it's position. this method modifies the orignal array. use splice method to delete or to add multiple items. (shift method will delete the first item at the begining and then you can assign the deleted item to an variable, to access later)

    let geek = ["mohammad yasin", "mess shahadat", "ekon", "mohammad emon", "antor das"];

    let geekShift = geek.shift();//if you save the array with shift method in a variable, then that variable returns the deleted array item
    document.write(geek + "<br>");
    document.write(geekShift);










    // pop method can remove single element from the end of an array. it removes the last element of an array with it's position. use splice method to delete or to add multiple items. this method modifies the orignal array

    let geek = ["mohammad yasin", "mess shahadat", "ekon", "mohammad emon", "antor das"];

    let geekPop = geek.pop();//if you save the array with pop method in a variable, then that variable returns the deleted array item. (shift method will delete the last item from the end of an array and then will assign the deleted item to this variable)
    document.write(geek + "<br>");
    document.write(geekPop);
</script>