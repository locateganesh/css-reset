# css-reset
A small bunch of code for css reset and css hacks.

    *{
       -webkit-box-sizing:border-box;
       -moz-box-sizing:border-box;
       box-sizing:border-box;
       outline:0
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
        font-synthesis:none;
        -webkit-text-rendering:optimizeLegibility; 
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
        border:1px solid #000;
    }
    input[type="tel" i]{padding:0;}
    input[type="tel" i]:focus{outline-offset:0}
    select{
        -webkit-appearance:none;
        -moz-appearance:none;
        appearance:none;
    }
    button:focus, input:focus, a:focus, a:active, select:focus{
        outline:0;
    }
    button::-moz-focus-inner, input::-moz-focus-inner, a::-moz-focus-inner, select::-moz-focus-inner, option::-moz-focus-inner{
        border:0;
    }
    select:focus:-moz-focusring {
      color:transparent;
      text-shadow:0 0 0 #585858;
    }
    input[type="tel" i]:disabled, input:disabled{
        color:inherit;
        opacity:1;
        -webkit-text-fill-color:#585858;
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
    .clearfix:before, .clearfix:after {
      content:"";
      display:table;
    }
    .clearfix:after {
        clear:both;
    }
