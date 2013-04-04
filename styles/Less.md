LESS Style Guide
================
###Keep children under parents. Don't duplicate code that doesn't need to be there.

Make sure your tabs are set to 4 spaces. You can do this in Sublime Text
View > Indentation > Tab Width: 4

````
a {

    color:@link_color;

    a:hover {
       
        color:@link_hover;
        outline:none;
       
    }
}


#something {
   
    color:@white;
    background:@primary;
   
    .classname {
       
        ul {
           
            list-style:none;
           
            li {
               
                float:left;
                margin-left:0.5em;
           
            }
        }
    }
}
````


When compiled, LESS will clean this up all nice and pretty-like. So, we have a nice LESS file that us humans can read, and a compressed and compiled CSS file for the robots/internet.

When labeling ares of a LESS/CSS document, please refrain from adding extra characters.

Example:
````
/* ----------Name of the area of the app ------------------------*/
````
Should be less, no pun intended, like this.
````
// Title
````
LESS allows for the "//" at the beginning of a comment. It will remove when CSS is compiled so as to make the CSS file as efficient as possible.


#Javascript
###USE JAVASCRIPT SPARINGLY

We have things like HTML5 and CSS3 to do a lot of stuff now. If you need javascript, check to see what ways you can do it with these other modern methods. There might even be a way to render class or ID names with Django. Ask a dev friend for some help.

If you ever look at something and think, "this seems like a lot of code", dig a little deeper and see if there is a better practice.
