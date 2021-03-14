# js dates




## creating dates, date methods (set date methods, get date methods), retrieving date name function from numbers, format date & time.



<script>
    /*
    By default, JavaScript will use the browser's (clients) time zone and display a date as a full text string like below:
    Tue Mar 02 2021 17:35:02 GMT+0600 (Bangladesh Standard Time)

    and if client machines date and time is incorrect, your script will reflect that incorrect date & time. Date objects created by programmers are static. The computer time is ticking, but date objects are not (so you will see the current time only when you refresh the browser. new date object will not be updated in realtime by default)

    Note: JavaScript counts months from 0 to 11. (0-> january, 1-> february, 2-> march and so on...)
    Note: JavaScript counts day from 0 to 6. (0-> sunday, 1-> monday, 2-> tuesday and so on...)
    Note: JavaScript counts month date from 1 to 31. (1 january, 2 january, 3 january)
    Note: JavaScript counts hours from 0 to 23.
    Note: JavaScript counts seconds and minutes same from 1 to 59.

    There are 4 ways (4 types of parameter) to create a new date object:
    new Date()
    new Date(year, month, day, hours, minutes, seconds, milliseconds)
    new Date(milliseconds)
    new Date(date string)
    */



    //new Date() creates a new date object with the current date and time
    let tarikh = new Date();

    document.write(tarikh);












    //retrieve date from milliseconds


    //new Date(milliseconds) creates a new date object as Thu Jan 01 1970 08:24:00 GMT+0600 (Bangladesh Standard Time)
    let tarikh = new Date(8640000);

    //new Date(milliseconds) creates a new date object as Tue Mar 02 2021 18:10:33 GMT+0600 (Bangladesh Standard Time)
    let tarikh2 = new Date(1614687033780);


    document.write(tarikh + "<br>");
    document.write(tarikh2 + "<br>");


















    /*
    new Date(year, month, ...) creates a new date object with a specified date and time. you need to specify 7 parameter as numbers -> year, month, day, hour, minute, second, and millisecond (in that order). you can omit (leave out) some of the arguments
    new date (year, month, day(date), hour, minute, second, and millisecond). dayName will be shown by default according to your date, you don't need to pass any day parameter
    */

    // if you give 7 arguments you are giving -> year, month, day, hour, minute, second, and millisecond
    let tarikh1 = new Date(2020, 0, 31, 12, 30, 30, 0);

    // if you give 6 arguments you are giving -> year, month, day, hour, minute and second
    let tarikh2 = new Date(2020, 0, 31, 12, 30, 30);

    // if you give 5 arguments you are giving -> year, month, day, hour and minute
    let tarikh3 = new Date(2020, 0, 31, 12, 30);

    // if you give 4 arguments you are giving -> year, month, day and hour
    let tarikh4 = new Date(2020, 0, 31, 12);

    // if you give 3 arguments you are giving -> year, month and day
    let tarikh5 = new Date(2020, 0, 31);

    // if you give 2 arguments you are giving -> year and month 
    let tarikh6 = new Date(2020, 0);

    //if you only give 1 argument, it will count as milliseconds not year.
    let tarikh7 = new Date(2020);

    document.write(tarikh1 + "<br>");
    document.write(tarikh2 + "<br>");
    document.write(tarikh3 + "<br>");
    document.write(tarikh4 + "<br>");
    document.write(tarikh5 + "<br>");
    document.write(tarikh6 + "<br>");
    document.write(tarikh7 + "<br>");








    // new Date(dateString) creates a new date object from a date string (date types: iso date, short date, long date)
    let tarikh1 = new Date("February 1, 2020 4:30:23"); //created via long date type

    document.write(tarikh1);







    /*(javascript month or day count start from 0 but these doesn't work in string date type (means month and day start from 1), and you need to write exact same format as below, even one single space will return error, and you need to give all the parameters inside string)
    date types :
    
    
    iso date --> "YYYY-MM-DDTHH:MM:SS" --> "2020-02-01T04:35:59" //do not give milliseconds
    (date and time is separated with a capital T and )
    
    
    short date --> "MM/DD/YYYY" --> "02/01/2020" 
    ("YYYY/MM/DD" or "DD/MM/YYYY" - writing in this format will return undefine. some browser's will try to guess the number, some will return NaN, and if don't writing zeros before a single month or a single day digit,then it can also return error)
    
    
    long date --> "MMM DD YYYY" --> "Feb 01 2020" (written in abbreviated -> jan) or "February 01 2020" (written in full)
    (you can separate them with coma but those will be ignore, and this long date type is case incensetive, month and day (date) can be in any order)
    */

    document.write(new Date("2020-02-01T04:35:59"));// iso date type
    document.write("<br>");


    document.write(new Date("02/01/2020"));//short date type
    document.write("<br>");

    document.write(new Date("Feb 01 2020"));//long date type
    document.write("<br>");






    //date methods:

    //set date methods
    let tarikh = new Date();

    tarikh.setHours(4);
    document.write(tarikh + "<br>");
    tarikh.setMinutes(30);
    document.write(tarikh + "<br>");
    tarikh.setSeconds(49);
    document.write(tarikh + "<br>");
    tarikh.setDate(1);
    document.write(tarikh + "<br>");
    tarikh.setMonth(1);
    document.write(tarikh + "<br>");
    tarikh.setFullYear(2020);//you can set only year with this method if you want
    document.write(tarikh + "<br>");
    tarikh.setFullYear(2022, 2, 1);//you can also give month and date. (year, month, day)















    // get date methods (will return numbers not strings like january or saturday):

    // this object has all the current year, month, date, hour, minute, second, millisecond, time. we will get / retrieve these values from this object via get date methods
    let tarikh = new Date();

    document.write("hour: " + tarikh.getHours() + "<br>"); // returns 0 to 23 (hour)
    document.write("minute: " + tarikh.getMinutes() + "<br>"); // returns 0 to 59 (minutes)
    document.write("second: " + tarikh.getSeconds() + "<br>"); // returns 0 to 59 (seconds)
    document.write("year: " + tarikh.getFullYear() + "<br>"); // returns the year (year)
    document.write("month: " + tarikh.getMonth() + "<br>"); // returns 0 to 11 (month) (index type)
    document.write("date: " + tarikh.getDate() + "<br>"); // returns date (date)
    document.write("day: " + tarikh.getDay() + "<br>"); // returns 0 to 6 (day) (index type)













    // retrieve month and day name:

    let tarikh = new Date(); // initialize current year, month, date, time, hour, minute, second, millisecond.

    let monthNumber = tarikh.getMonth(); // retrieve month number

    let dayNumber = tarikh.getDay(); // retrieve day number

    function getMonthName(monthNumber) {
        monthNames = ['january', 'february', 'march', 'april', 'may', 'june', 'july', 'august', 'september', 'october', 'november', 'december'];
        return monthNames[monthNumber];
    }

    function getDayName(dayNumber) {
        dayNames = ['sunday', 'monday', 'tuesday', 'wednesday', 'thursday', 'friday', 'saturday'];
        return dayNames[dayNumber];
    }

    document.write("month Name: " + getMonthName(monthNumber) + "<br>");
    document.write("day Name: " + getDayName(dayNumber) + "<br>");













    // format date and time:

    let tarikh = new Date(); // initialize current year, month, date, time, hour, minute, second, millisecond.

    function formatedDate(dateOb) {
        let date = dateOb.getDate();
        let month = dateOb.getMonth();
        month++;
        let year = dateOb.getFullYear();

        return date + "-" + month + "-" + year; //2-3-2021
    }

    document.write(formatedDate(tarikh));



    //convert date to string

    document.write(tarikh.toString() + "<br>"); // Tue Mar 02 2021 21:02:40 GMT+0600 (Bangladesh Standard Time)
    document.write(tarikh.toUTCString() + "<br>"); // Tue, 02 Mar 2021 15:02:40 GMT
    document.write(tarikh.toGMTString() + "<br>"); // Tue, 02 Mar 2021 15:02:40 GMT
</script>