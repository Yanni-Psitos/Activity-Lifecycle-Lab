
---

| Title | Type | Duration | Name | City |
| --- | --- | --- | --- | --- |
| Activity Lifecycle | Lab | "1:00" | James Davis | NYC |

---  
# Activity Lifecycle Lab

## Introduction

Below, you will find three scenarios, and questions following each one.

To the best of your ability, answer the questions **in english**, not in code.

Below the scenarios, you will find a few questions. Answer those however you'd like.

Answer the questions by editing this readme, pushing your changes to your forked repo, and making a pull request.

## Exercise  


####Scenario 1:

Let’s say you made a To Do list app, where you can add things to a list and cross them off. You decide to cross some items off the list and mark them as complete.

When you rotate the device, the things you marked as complete are no longer crossed off.

**Question**: Why did this happen?
<br />Answer: <i>This happened because the activity containing the 'crossed off' data was destroyed when orientation changed. </i>

**Question**: How do you fix this issue?
<br />Answer: <i>Store the data internally using SharedPreferences and Editor and within onCreate add the data that crosses the text off by calling SharedPreferences (if it is not null). You can also use the onSavedInstance method to save the state and call it again in onCreate (using the bundle and onSavedInstance)</i>


####Scenario 2:

The Amazon Kindle Android app allows you to open and read eBooks. You discovered a bug! You opened a book, and read it from the beginning up to page 68. Then, you left the app and closed it completely so you can do other things.

When you opened the app again, and opened the book, it started from page 1 (and not page 68 where you left off)!

**Question**: How would you fix this issue?
<br />**Answer**: <i>By using onPause to store the data (or, in this instance, page number), and pulling it up again within onResume, and having SharedPreferences to store the data internally (because closing the app is destroying the activity).</i>


####Scenario 3:

Facebook for Android added a feature last year where, if you started writing a comment on someone’s post and decided not to do so, the app would save a draft of it just in case you changed your mind.

Take this scenario. On a post on Facebook, you click the “comment” button (which opens a new CommentActivity). You start writing a comment, and then change your mind by pressing the back key (which closes the CommentActivity). You click on the “comment” button again, and in the newly-opened CommentActivity, the comment you were writing is still there.

**Question**: How would you implement this feature? Be specific; what lifecycle methods would you use in CommentActivity, and what techniques would you use?
<br />**Answer**:<i>By using SharedPreferences to store the data when onPause() is called, and call it again when onResume() is called when the activity is created again.</i>



In your own words…
==================

**Question**: What are the methods of the Activity Lifecycle?
<br />**Answer**: <b>onCreate():</b> Creates the activity. 
<b>onStart():</b> Begins to implement the layout and functions. 
<b>onResume():</b> Starts the activity for the user.
<b>onPause():</b> Pauses the activity if the main activity begins a new activity, as well as occurring before an activity is stopped (onPause makes the activity run in the background). 
<b>onStop():</b> Stops the activity entirely. 
<b>onDestroy():</b> Destroys the activity, requiring it to be restarted through onCreate.

**Question**: What order are the methods called?
<br />**Answer**: <i>onCreate,onStart,onResume(app is running), onPause, onStop, onDestroy.</i>

**Question**: What is a bundle?
<br />**Answer**: <i>Bundles hold data and allow them to be passed through instance states.</i>

**Question**: How do you get the Shared Preferences of an app?
<br />**Answer**: <i>Initialize a SharedPreferences method: </i>SharedPreferences sharedPreferences = getSharedPreferences("KEY_NAME",Mode_PRIVATE);
<i>Create an editor: </i> Editor editor = sharedPreferences.edit();
<i>Fill the editor: </i> editor.put("KEY", VARIABLE);
<i>Save/Commit the data: </i> editor.commit();
<i>Get the data by repeating the first couple steps.: </i>




