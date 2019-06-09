# CSS Reset 
CSS reset is small css properties which overrides the browser default properties also solves some cross-browser compatibility issue.

## Why css reset?
Every browser has its own default styling like header (*h1, h2, h3*...) , *p*, *body*, form elements (*input*, *select*, *textarea*) and other elements. It is called **user agent stylesheet**. To remove default user agent style css reset can help.

    *{
        -webkit-box-sizing:border-box;
        -moz-box-sizing:border-box;
        box-sizing:border-box;
     }

`box-sizing` initial and default value is `content-box` as specified by the CSS standard. The width and height properties include the content, but does not include the padding, border, or margin. For example, `.box {width:50px; height:50px; padding:20px; border:2px solid red;}` renders a box that is 94px wide.

You want your box to be the same as you defined after `border` and `padding` property. That why give this property with * which applies to every element. About browser prefix (`-webkit-`, `-moz-`). `box-sizing` browsers compatibilities are **chrome** *(10.0, 4.0 -webkit-)*, **Mozilla** *(29.0, 2.0 -moz-)*, **IE/Edge** *(8.0)*, **Safari** *(5.1, 3.2 -webkit-)*. It's better to give browser prefix.

    .no-outline *{
       outline:0;
    }

Every anchor tag (`<a href=""></a>`), form elements (`input`, `select`) has a default blue in chrome and dotted **outline** in Mozilla. If you don't want this you can give class `.no-outline` to the body which disabled outline to every element.

    body, button, p{
       margin:0;
    }
    
`body` has user agent margin which everyone overrides first thing. Also, `p` you can remove margin and give a margin of your own choice.

> `button` has some hidden margin which is visible in safari browser. If you position the button absolutely bottom you can see `1px` gap in iPhone  and when you give margin 0 to button it solves.

    a{
      text-decoration:none;
      color:inherit;
    }
    
On anchor tag (`<a href=""></a>`) `text-decoration:none` property removes underline but blue link color still there. For that, with `color:inherit` propery anchor tag takes its parent color. 

     img{
       border:0;
     }
      
Some browsers have boder on image. it's better to remove border from all `img` tag.

     button{
        cursor:pointer;
     }
      
HTML buttons don't have cursor pointer ([know why in details](https://ux.stackexchange.com/a/105098/66387)).

     h1, h2, h3, h4, h5, h6{
        font-weight:normal;
        margin:0;
        font-size:inherit;
     }

This is optional property when you don't want default browser title styling. You can define your own or you can remove it.

    body{
        font-family:sans-serif;
        font-size:16px;
        line-height:1.4;
        color:#3B3B3B;
        -webkit-font-smoothing:antialiased;
        -moz-osx-font-smoothing:grayscale;
        -webkit-tap-highlight-color:rgba(0,0,0,0);
    }
    
`font-family` needs to define. `line-height: 1.4` is most preferably used.  
**`-webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale;`**: Smooth the font on the level of the pixel, as opposed to the subpixel. Switching from subpixel rendering to antialiasing for light text on dark backgrounds makes it look lighter. This property is useful for safari browser because most fonts look bold in safari.
**`-webkit-tap-highlight-color`**: On tap links to buttons, you can see a light blue highlight on iOS safari. This property removes it.

    input, textarea, button, select{
        font-family:inherit;
        font-size:inherit; 
        background:none; 
        border-radius:0;
        outline:0; 
        padding:0;
        border:1px solid;
     }
     
All these user input fields have default property which doesn't get auto override until and unless you do it manually or you can make the style like `font-family`, `font-size` **inherit** to its parent.   
Safari iOS devices have default radius border. **`boder-radius:0`** property removes it.  
Also, every browser has its own padding for input field which is different from each other.

     select.no-arrow, input, textarea, button{
        -webkit-appearance:none;
        -moz-appearance:none;
        appearance:none;
     }
     
To remove default dropdown from select give class `no-arrow` to select or you can define `appearance: none` globally to select which removes dropdown arrow.  
In iOS safari, input fields have a shadow at top. which looks like this: 
![iOS safari input appearance](https://s16.postimg.cc/q9eluejl1/ios5_input.png) 
Property `appearance: none` helps to remove it.

     select:focus:-moz-focusring {
       color:transparent;
       text-shadow:0 0 0 #585858;
     }
     
Mozilla firefox has a dotted outline on focus of select and this is a hack to remove outline.

     input[type="tel" i]{
        padding:0;
     }
     input[type="tel" i]:focus{
        outline-offset:0
     }
     
Remove default padding and outline from `<input type="tel">`.

     input[type="tel" i]:disabled, input:disabled{
         color:inherit;
         opacity:1;
         -webkit-text-fill-color:#585858;
     }
     
Disabled input fields have a color with some opacity in safari. To make disabled input like regular input give above property and you can give `color` and `-webkit-text-fill-color` of your choice. 

     button:focus, input:focus, a:focus, a:active, select:focus{
         outline:0;
     }
     button::-moz-focus-inner, input::-moz-focus-inner, a::-moz-focus-inner, select::-moz-focus-inner, option::-moz-focus-inner{
         border:0;
     }
     
So solve pseudo classes outline and border visible on mozilla and other browsers.  

     .clearfix:before, .clearfix:after {
       content:"";
       display:table;
     }
     .clearfix:after {
         clear:both;
     }
     
Use clearfix when working with float properties. 

     
    *{
        -webkit-box-sizing:border-box;
        -moz-box-sizing:border-box;
        box-sizing:border-box;
     }
     .no-outline *{
        outline:0;
     }
     body, button, p{
        margin:0;
     }
     a{
        text-decoration:none;
        color:inherit;
     }
     ul{
        padding:0;
         margin: 0;
     }
     ul li{
        list-style:none;
     }
     img{
        border:0;
     }
     button{
        cursor:pointer;
     }
     h1, h2, h3, h4, h5, h6{
        font-weight:normal;
        margin:0;
        font-size:inherit;
     }
     body{
        font-family:sans-serif;
        font-size:16px;
        line-height:1.4;
        color:#3B3B3B;
        -webkit-font-smoothing:antialiased;
        -moz-osx-font-smoothing:grayscale;
        -webkit-tap-highlight-color:rgba(0,0,0,0);
     }
     input, textarea, button, select{
        font-family:inherit;
        font-size:inherit; 
        background:none; 
        border-radius:0;
        outline:0; 
        padding:0;
        border:1px solid;
     }
     select.no-arrow, input, textarea, button{
         -webkit-appearance:none;
        -moz-appearance:none;
         appearance:none;
     }
     select:focus:-moz-focusring {
       color:transparent;
       text-shadow:0 0 0 #585858;
     }
     input[type="tel" i]{padding:0;}
     input[type="tel" i]:focus{outline-offset:0}
     input[type="tel" i]:disabled, input:disabled{
         color:inherit;
         opacity:1;
         -webkit-text-fill-color:#585858;
     }
     button:focus, input:focus, a:focus, a:active, select:focus{
         outline:0;
     }
     button::-moz-focus-inner, input::-moz-focus-inner, a::-moz-focus-inner, select::-moz-focus-inner, option::-moz-focus-inner{
         border:0;
     }
     .clearfix:before, .clearfix:after {
       content:"";
       display:table;
     }
     .clearfix:after {
         clear:both;
     }
     ::-webkit-input-placeholder { 
       color:#a9a9a9;
     }
     ::-moz-placeholder { 
       color:#a9a9a9;
     }
     :-ms-input-placeholder { 
       color:#a9a9a9;
     }
     :-moz-placeholder { 
       color:#a9a9a9;
     }
