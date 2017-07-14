# RWD



Lesson11. Image with Markup 

sometimes it's much better to use Text than img 

Webfonts

### Text Problems

[Text as image](http://udacity.github.io/responsive-images/examples/2-02/textAsImage)

[Text as image over photo](http://udacity.github.io/responsive-images/examples/2-02/textAsImageOverPhoto)

[Text using Web Font](http://udacity.github.io/responsive-images/examples/2-02/textAsText)

[Text as text, over photo](http://udacity.github.io/responsive-images/examples/2-02/textAsTextOverPhoto)



![](https://www.smashingmagazine.com/wp-content/uploads/2013/01/chart-css3.png)



https://www.smashingmagazine.com/2013/04/build-fast-loading-mobile-website/

display: none과 hidden use @media query 







## JavaScript Fundamental



### Data & Datatypes

+ Primitive type

Number , String , boolean , undefined, null

+ function, object,array



### Comments

//  good comments makes better code :D it 'll  help for reading code 



### Variables 

```
var name ="Chany";
```

It's memory for data 



### Escaping /

 

| **Code** | **Character**     |
| -------- | ----------------- |
| \        | \ (backslash)     |
| \"       | '' (double quote) |
| \'       | ' (single quote)  |
| \n       | newline           |
| \t       | tab               |



```
"The file located at "C:\\Desktop\My Documents\Roster\names.txt" contains the names on the roster."
```



Lesson 2: Data Types & variables 

Quiz 12. Create a string with the name of your favorite food. The first letter of the string should be capitalized.

I think it's right first letter of string is capitalized  

/*

* Programming Quiz: Favorite Food (2-3)
   */
   var favoritefood =["Pasta","Pizza","Hamburger"]
   console.log(favoritefood[0]);

but It's wrong why?



### Null vs Undefined

null value or nothing  empty 

undefined absence of value  not yet value 



## types 



**DEFINITION:** A **strongly typed language** is a programming language that is more likely to generate errors if data does not closely match an expected type. Because JavaScript is loosely typed, you don’t need to specify data types; however, this can lead to errors that are hard to diagnose due to implicit type coercion.





Quiz 20 also I wonder 



/*

* Programming Quiz: Semicolons! (2-8)
   */
    var thingOne ="red";
    var thingTwo = "blue";

console.log(thingOne, thingTwo);

/*



The value of thingOne wasn't printed to the consoleundefined?????





## Conditionals

FlowCharts 





Quiz 7 

```
/*
 * Programming Quiz: Musical Groups (3-3)
 */

// change the value of `musicians` to test your conditional statements
var musicians = 1;

if(musicians > 3){
    console.log('this is a large group');
}
else if(musicians === 3){
    console.log('trio');
}
else if(musicians === 2){
    console.log('duet');
}
else if(musicians === 1){
    console.log('solo');
}
else{
   console.log("not a group"); 
}
I wonder why is it wrong?.? 

```













## Loops

