# 0716 image with Mark up

### [Div with background image](http://udacity.github.io/responsive-images/examples/2-06/divWithBackgroundImage)

### [CSS background-size: cover](http://udacity.github.io/responsive-images/examples/2-06/backgroundSizeCover)

### [Body with background image](http://udacity.github.io/responsive-images/examples/2-06/bodyWithBackgroundImage)

### [Body with background image and gradient](http://udacity.github.io/responsive-images/examples/2-06/bodyWithBackgroundImageAndGradient)

### [Body with elaborate background using only CSS](http://udacity.github.io/responsive-images/examples/2-06/bodyWithElaboratePatternPureCSS)

### [Using CSS background images for conditional image display](http://udacity.github.io/responsive-images/examples/2-06/backgroundImageConditional)

### [Using CSS background images for alternative images](http://udacity.github.io/responsive-images/examples/2-06/backgroundImageAlternative)

### [image-set()](http://udacity.github.io/responsive-images/examples/2-06/imageSet)



## background-size cover and contain







## unicode

Example: [Unicode instead of an image](http://udacity.github.io/responsive-images/examples/2-08/unicodeStar)

[Unicode character sets](http://unicode-table.com/en/sets/)

[List of Unicode characters](http://en.wikipedia.org/wiki/List_of_Unicode_characters)

[Here's a big list of unicode characters.](http://unicode-table.com/)

[More on meta tag charsets](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta)



## iconfont

[weloveIconfonts](http://weloveiconfonts.com/)



iconfonts의 사용 why? 웹폰트의 사용은 색 변화 사이즈 조절에 용이하기 때문에 ! 

그리고 아마 색감이 없는 것은 파일 사이즈도 더 줄 일 수 있을 것.. 이부분은 애매 



## svg

# Inlining Images With SVG And Data URIs

Examples:

- [SVG Data URI in HTML](http://udacity.github.io/responsive-images/examples/2-11/svgDataUri)
- [SVG Data URI in CSS](http://udacity.github.io/responsive-images/examples/2-11/svgDataUriCss)
- [SVG text on a path](http://udacity.github.io/responsive-images/examples/2-11/svgTextOnAPath)
- [SVG optimized and unoptimized](http://udacity.github.io/responsive-images/examples/2-11/svgUnoptimisedAndOptimised)

------

[Browser support for inline SVG](http://caniuse.com/#feat=svg-html5)

[Browser support for Data URIs](http://caniuse.com/datauri)

[SVG Optimiser](http://petercollingridge.appspot.com/svg-optimiser)

[Trajan's Column SVG example](http://upload.wikimedia.org/wikipedia/commons/6/6c/Trajans-Column-lower-animated.svg)

[20 examples of SVG that will make your jaw drop](http://www.creativebloq.com/design/examples-svg-7112785)

[SVG animation examples](http://codepen.io/chrisgannon/)



IE8이상 지원하니 svg 크로스브라우징 고민 그닥 없이 씁시다. 



이거 강의 하나하나가 공부해야 될 걸 엄청 던져주시는 구마이 

svg inline은 http요청을 줄여준다! (data-uri)



자주 여는 것은 외부파일로 캐쉬로 할 수 있게 하는 것이 더 유리할 수 있다. 

그떄 그때 다름 



# Srcset

**Spot the deliberate mistake!**

At around 2:30 you'll see that Firefox chooses wallaby_1x.jpg even with srcset turned on. That's because we did the screencast on a 1x display :^).

------

Examples:

- [srcset with w values](http://udacity.github.io/responsive-images/examples/3-03/srcsetWValues)
- [srcset with w values, 50vw](http://udacity.github.io/responsive-images/examples/3-03/srcsetWValues50vw)

------

A fun article on srcset

 

[Device pixel density list](http://pixensity.com/list/phone)

[More information about working with pixel density](http://www.html5rocks.com/en/mobile/high-dpi/)

[Working with h units](https://github.com/ResponsiveImagesCG/picture-element/issues/86)

[Wikipedia wallabies](https://en.wikipedia.org/wiki/Wallaby)



[img srcset ](https://www.smashingmagazine.com/2014/05/responsive-images-done-right-guide-picture-srcset/) 

+ width 크기에 따라 대응 시킬 수 있고  요런식으로 500w 1000w 이런식으로 브라우저 width에 대응하여 img 를 결정 
+ pixel Ratio 1x,2x,3x이런식으로 대응 시킬 수 있다 ! 
+ viewport 비율에 따라 대응 50vw 100vw 



```html
<img class="w" src="images/Coffee_1280w.jpg" srcset="images/Coffee_1280w.jpg 1280w, images/Coffee_640w.jpg 640w" sizes="(max-width: 960px) 50vw, 100vw" alt="Coffee by Amy March from Turkey">
```

window.devicepixelRatio

1.25;The Picture Element



## The Picture Element

 source It's alternative source :D 

source also can sue media query :D 

```html
<picture>
    <source media="(min-width: 650px)" srcset="kitten-large.png">
    <source media="(min-width: 465px)" srcset="kitten-medium.png">
    <img src="kitten-small.png" alt="Cute kitten">
  </picture>
```







Example:

- [Picture element: alternative image formats](http://udacity.github.io/responsive-images/examples/3-06/pictureAlternativeFormats)

------

[More information about WebP](https://developers.google.com/speed/webp/?csw=1)



# The Full Monty

Examples:

- [Picture element: art direction](http://udacity.github.io/responsive-images/examples/3-08/pictureArtDirection)
- [Picture element: with srcset and media queries](http://udacity.github.io/responsive-images/examples/3-08/pictureFullMonty)
- [Picturefill polyfill](http://udacity.github.io/responsive-images/examples/3-08/picturefill)

------

Images are by [Jon Q](https://twitter.com/itsjonq) from Pearl Chen's HTML5 Rocks article [Built-in Browser Support for Responsive Images](http://www.html5rocks.com/tutorials/responsive/picture-element/).

You can download Picturefill [here](http://scottjehl.github.io/picturefill/).

[Element Queries](https://responsiveimagescg.github.io/cq-usecases/) will work like Media Queries, but with reference to the size of an element's parent container rather than viewport size. Browser implementation is in progress and in the meantime there's a polyfill [here](https://github.com/marcj/css-element-queries).

Lots of other `<picture>` use cases, examples and code snippets are available [here](https://dev.opera.com/articles/responsive-images/).

Find out more about responsive images from the [Responsive Images Community Group](http://responsiveimages.org/).



# Accessibility

### [Here's Lynx](http://invisible-island.net/lynx/)

### [Here's ChromeVox](http://www.chromevox.com/)

### [Here's the site Cam uses](http://udacity.github.io/responsive-images/examples/3-04/forARIA/index.html)

### General advice about alt attributes

- `alt` attributes should be descriptive for important images, like this body surfer. Because body surfing is important, I guess.
- `alt` attributes should be empty for images that are just decorations, like this boiler image. Do you get the joke? It's a boiler to represent boiler plate code, which is sometimes empty of content.
- `alt` attributes should be set on every image, just like this pig is set on being so darn cute.





## Lesson12. Quiz 10

# 퀴즈: Project Part 3

### Download the [RI-Project-Part-3-Start.zip](http://udacity.github.io/responsive-images/downloads/RI-Project-Part-3-Start.zip).

### [Picture polyfill](http://scottjehl.github.io/picturefill/)

### [Responsive Images Community Group](http://responsiveimages.org/)

Make sure you are running the [Udacity Feedback Chrome Extension](https://chrome.google.com/webstore/detail/udacity-front-end-feedbac/melpgahbngpgnbhhccnopmlmpbmdaeoi) so that you get feedback.

**Note:** under certain screen conditions, you will no longer meet the < 1.5 MB limit for your images from part 1 of the project. That's ok! The only tests that matter for this quiz are in the section that says "Project Part 3".*

You can download [ri-project-part-3-solution.zip](https://d17h27t6h515a5.cloudfront.net/topher/2016/June/575fa008_ri-project-part-3-solution/ri-project-part-3-solution.zip) to compare your solution.



## Javascript condtion

### 8 Murder Mystery 

아 c8 영어 진짜 ㅜㅜ 읽기 싫어진다. 

### 9 More Complex Problems



### 10 Logical Operations

| **Operator** | **Meaning** | **Example**        | **How it works**                         |
| ------------ | ----------- | ------------------ | ---------------------------------------- |
| `&&`         | Logical AND | `value1 && value2` | Returns `true` if **both** `value1` **and** `value2` evaluate to `true`. |
| `||`         | Logical OR  | `value1 || value2` | Returns `true` if **either** `value1` **or** `value2` (**or even both!**) evaluates to `true`. |
| `!`          | Logical NOT | `!value1`          | Returns the **opposite** of `value1`. If `value1` is `true`, then `!value1` is `false`. |



I wonder 

```
3 < -10 [BLANK] "James" !== "james"
```

the answer is ||

why?????

3< -10 false 

|| 

false || James -> True 

James !== James -> false?





## Short-circuiting  (Validation)

![In some scenarios, the value of `B` in logical AND and OR doesn't matter.](https://d17h27t6h515a5.cloudfront.net/topher/2016/November/5834b9be_short-circuiting/short-circuiting.png)





````
A-> false -> false 
A-> true -> true 

var data = data || 1; 
````



### Quiz  Checking your balance :D  



```
var balance = 325.00;
var checkBalance = true;
var isActive = false;

// var checkValance =prompt("Check your balance?");
if(checkBalance){
    if(isActive && balance>0){
        console.log("Your balance is $"+balance+".");
    }
    else{
        if(!isActive){
            console.log("Your account is no longer active")
        }
        else{
            if(balance === 0){
              console.log("Your account is empty")  
            }
            else{
              console.log("Your balance is negative please contanct bank")
            }
        }
    }
    
}
else{
 console.log("Thank you Have a nice day")
}
```



뭐지 맞게 한 것 같은데 왜 안나오지?





Quiz 3-7 

Ice Cream

What do i Wear 



## Truthy & Falsy

false,null,undefined, 0,"",NaN

### Here’s *the* list of all of the falsy values:

1. the Boolean value `false`
2. the `null` type
3. the `undefined` type
4. the number `0`
5. the empty string `""`
6. the odd value `NaN` (stands for "not a number", check out the [`NaN` MDN article](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN))

That's right, there are only *six* falsy values in all of JavaScript!



## Ternary operator 

The **ternary operator** provides you with a shortcut alternative for writing lengthy if...else statements.

```
conditional ? (if condition is true) : (if condition is false)
```



삼항 연산자 ?

가독성 떄문에 간단한 코드 일 떄 삼항 연산자로 작성 



## 18 Quiz Navigation the Food C...

 ```

    eatsPlants ? category = eatsAnimals ? "omnivore" : "herbivore"
     : category = eatsAnimals ? "carnivore" : category
 ```



## 19  Switch Statement 

```
var option = 3;

switch (option) {
  case 1:
    console.log("You selected option 1.");
    break;
  case 2:
    console.log("You selected option 2.");
    break;
  case 3:
    console.log("You selected option 3.");
    break;
  case 4:
    console.log("You selected option 4.");
    break;
  case 5:
    console.log("You selected option 5.");
    break;
  case 6:
    console.log("You selected option 6.");
    break; // technically, not needed
}
```



## 20 Falling-through

공통으로 놓고 이용하기도 한다. break를 안 쓰고 

```
var prize = "";

switch (winner) {
  case 1:
    prize += "a trip for two to the Bahamas and ";
  case 2:
    prize += "a four piece furniture set.";
    break;
  case 3:
    prize += "a smartwatch and ";
  default:
    prize += "tickets to the circus.";
}
```



## 21 Quiz Back to School











http://responsiveimages.org/



## lotterySystem

1. 그냥 셔플이여서 맘에 안드는데... ====> 예전 번호들이랑 비교하기 
2. 내가 몇개 선택하고 자동으로 채울 수 있게 하기 
3. 맘에 드는 번호는 저장
4. 일부만 변경 하기 
   로또 번호로도 갖가지 기능들을 넣을 수 있구나 _=
   너무 사이즈를 키우는 건 또 아닌지 싶지만 내가 사용자라면 저런거 있으면 다 좋을 것 같음 'ㅁ' 
   사이즈를 키운다 -> 나는 못한다 .. -> 으으 하게 만들어보자