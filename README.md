## Project Name:  Recipe Display Application

### Course Title:
Web Application Development

### Assignment Date:  
March 7, 2018

### Student Name:  
Laura Wright

### Project Description:
We used the JQuery methods fadeIn and animate to change the DOM. We coordinated the clicking of and hovering over headings to set off code in JQuery, to change the DOM. In index.html, we used to JQuery to display the ingredients and method when the user clicked on those headings. In index2.html, we used JQuery to toggle between the ingredients and method and change the color of the headings when we hovered over them and clicked on them.

### View Project Online:
(Replace this statement with your Github Page URL that was created when you 
 published the project.)

### Lessons Learned in the Assignment:
* We learned how to use JQuery to bring in extra content to the DOM in response to a user's action. We had the ingredients and method appear when the user clicked on either of these h3 headings. We used the following JQuery code:

function display(event) {
    
    $(event.currentTarget).next().fadeIn("slow");
    
}//end of display

  $("h3").click(display);
  
We firstly created a function called 'display' for the event. Using the $, we selected the currentTarget as our event, which refers in this case to the h3 heading. We then traversed the DOM to find the 'next' element in the DOM tree following the h3 headings. This accessed the ingredients and the method. The way in which we wanted the ingredients and method to appear was for them to fade in slowly. We then added an event listener in the last line of code that would call up the code and bring it into action. This last line of code means that when a user clicks on an h3 heading, the display function created above will execute. 

* We also used the JQuery method animate() to toggle between the ingredients and the method. 

function display2(event) {
 $(event.currentTarget).next().animate( {height: ‘toggle’}, “slow”);
}//end of display2

//attach event listener to h3 elements to invoke display function when clicked
$("h3").click(display2);


We created a function called 'display2' for this event, and within the function we took the currentTarget which is the clicking of the h3 heading, got its next element which was the ingredients or method, and then toggled slowly between them. The event listener that was used to call up this function stated that when the user clicked on the h3 heading, the display2 function would be called into action.


* We learned how to change the color of the h3 heading using JQuery. The color of the heading changed twice, once when the user first hovered over the heading and then when the mouse left the heading.

$("h3").hover(function(){
 $(this).css("background-color", "yellow");
 }, function(){
 $(this).css("background-color", "pink");
 });
 
 
$(“h3”).hover(display2);

We created a hover function that stated that when the user was on the current element (the h3 heading), the css background color would turn to yellow. Then when the mouse left the heading it would change to yellow. The last line of the code invokes the above function by saying that when the user hovers over the h3 heading, the display2 function will execute. The display2 function is mentioned earlier in the code, and this calling statement is referring to the hover aspect of the display function.


