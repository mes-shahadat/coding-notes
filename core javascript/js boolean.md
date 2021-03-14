# js boolean


## boolean, undefine, null (primitive data types, non-primitive data types)

<script>
    //Primitive data types are - byte, short, int, long, float, double, boolean and char / str
    //Non-primitive data types are - such as String, Arrays and Classes

    /*undefined vs null
    undefined means that object or value is not defined / initilized or defined as undefine (value set as not set)
    null means object is declared, but sending empty value. means the value is initilized as null (value set as null / empty / 0)
    */


    //boolean is built in object corresponding to the primitive boolean data type. javascript boolean can have one of two values: true or false

    //every data types that returns false boolean value
    let var1 = 0;// value == 0 is false
    let var2 = -0;// value == -0 is false
    let var3;// no parameter is false
    let var4 = "";// empty is false
    let var5 = NaN;// NaN (Not a Number) is false, even (NaN == NaN or NaN == anyDataType) is false.
    let var6 = null;// null is false, but (null == undefined) is true
    let var7 = undefined;// undefined is false.
    let var8 = false;// false is false

    if (var2) { //if var is true returns true, if var is false returns false.
        document.write("true");
    }
    else {
        document.write("false");
    }
</script>