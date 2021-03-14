# conditioning



## if, else if, else statements:

<script>
    var a = prompt('plz input the number:');

    //Use if to specify a block of code to be executed, if a specified condition is true
    if (a <= 39) {
        document.write('you have been failed');
    }
    //Use else if to specify a new condition to test, if the first condition is false
    else if (a <= 40) {
        document.write('you have passed closely');
    }
    else if (a <= 50) {
        document.write('you have passes good');
    }
    else if (a <= 60) {
        document.write('you have passed with best grade');
    }
    else if (a <=100){
        document.write('you have passed greatly');
    }
    //Use else to specify a block of code to be executed, if the previous condition gets false
    else {
        document.write("error !. wrong input. value is higer than 100")
    }
</script>














## switch statement:

<script>
    var a = prompt('type one: sat, sun, mon, tue, wed, thr, fri ') //expression

    //switch will match it's expression (any data type value) with case's expression, and only matched expression will be executed, expressions are case sensitive
    switch (a){
        case 'sat': // if  you want two or more cases to execute same code write one after other like this
        case 'mon':
        case 'tue':
        case 'wed':
        case 'thr':
            document.write('working day');
            break;// write break after every case statement, so other cases doesn't executes by themselves afterwards
        case 'fri':
        case 'sun':
            document.write('holiday');
            break;
        default: // default case will be executed if any expression doesn't matches
            document.write('wronge input')
    }
</script>


