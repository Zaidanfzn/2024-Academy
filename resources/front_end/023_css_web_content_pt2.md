## PHOTO SIZE
first we're gonna set how big is your photo that you want to show.

let's say we're gonna make it `width: 350px`, and having a rounded border around `5px`. so the size of `.myPic` is:
```css
.myPic{
    min-width: 350px;
    border: solid black; /* optional, it's just so you can see the size */
}
.myPic img{
    width: 100%; /* it makes your source follow the parents size, as for <img> the parent is .myPic */
    height: auto;
    border-radius: 0.5rem;
}
```


## TITLE
Before and After:

    +-------------------------------------------------+                         +-------------------------------------------------+
    |<div class=title>                                |                         |                                                 |
    |<div class=bio-container>                        |                         |                <div class=title>                |
    |                                                 |                         |                                                 |
    |                                                 |                         |<div class=bio-container>                        |
    |                                                 |         =====>          |                                                 |
    |                                                 |                         |                                                 |
    |                                                 |                         |                                                 |
    |                                                 |                         |                                                 |
    |                                                 |                         |                                                 |
    +-------------------------------------------------+                         +-------------------------------------------------+ 
    
so in the stylesheet you can add:
```css
#aboutMe .container{
    text-align: center;
}
.title{
    padding-top: 80px;
    padding-bottom: 50px;
    font-size: large;
}
```

## FLEX

Now we're gonna make the bio-container become:

Before and After:

    +-------------------------------------------------+                         +-------------------------------------------------+
    |                                                 |                         |                                                 |
    |              <div class=title>                  |                         |                <div class=title>                |
    |                                                 |                         |                                                 |
    |<div class=myPic>                                |                         |<div class=myPic><div class=myBio>               |
    |<div class=myBio>                                |         =====>          |                                                 |
    |                                                 |                         |                                                 |
    |                                                 |                         |                                                 |
    |                                                 |                         |                                                 |
    |                                                 |                         |                                                 |
    +-------------------------------------------------+                         +-------------------------------------------------+ 

the css is:
```css
.bio-container{
    display: flex;
}
```

With `display: flex` we can make it automatically become like *after*.

Flex container like above will have it's flex item to be aligned horizontally by default.

now make it centered with `justify-content: center;` or `justify-content: space-evenly;` if you want it has an evenly space between element.
```css
.bio-container{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}
```

With `flex-wrap` activated, it will make `.bio-container` responsive to the size of web and make it automatically become row after a certain width like.

               +-----------------------------+
               |           <navbar>          |          
               +-----------------------------+
               |     <div class="title">     |
               |    +-------------------+    |
               |    |                   |    |     
               |    |                   |    |     
               |    |                   |    |     
               |    | <div class=myPic> |    |    
               |    |                   |    |     
               |    |                   |    |     
               |    +-------------------+    |   
               |    +-------------------+    |
               |    |                   |    |     
               |    |                   |    |     
               |    |                   |    |     
               |    |<div class=myBio>  |    |    
               |    |                   |    |     
               |    |                   |    |     
               |    +-------------------+    |   
               |                             |
               +-----------------------------+

And we've make responsive `about me` content.

Next we're gonna talk about responsive web using `@media`.
