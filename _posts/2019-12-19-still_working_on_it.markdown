---
layout: post
title:      "Step by step"
date:       2019-12-19 19:45:53 -0500
permalink:  still_working_on_it
---

Writing has always been my weakest point...so when asked to write about a method/process which is clicking but when it comes to verbally discussing it out loud with a lead for some strange reason it all goes out the window, maybe it nerves?  Let's see if just typing it out is any better.....

Sinatra

"Regrets, I've had a few
But then again, too few to mention
I did what I had to do
And saw it through without exemption
I planned each charted course
Each careful step along the byway
And more, much more than this
I did it my way....."

Oh wait,  I quoted ole blue eyes.  Sinatra is more then Frank,  Sinatra shows the shows us the basics and understanding of routes as it is quite a change when you get to Rails.  Learning routes in Sinatra was like an old Atari game called Breakout, in the game your boucing back and forth essentially breaking through bricks and with routes you are bouncing back and forth.

In the example below (controller) I am requesting a route to go to a specific page, the route is '/chores/new' and what it's doing is requesting a view page 'chore' is a directory' and 'new' is an erb file.  

```
get '/chores/new' do
        authorize
        erb :'chores/new'
    end
		
		```
		
		What populates when I request the route:
		
		```
<form action="/chores" method="post">
    <label for="task">New Chore:</label><br>
    <textarea name="task" cols="30" rows="10"></textarea><br>
    <input type="submit" value="Post Chore">
</form>
```

Once I fill out my form I then have to do something with the information that is input into my form.  That's where method="post" comes into play.  The information is sent back to my contoller where it posts the information that was input into a database.  So when I say that routes remind me of Breakout you are essentially going back and forth between routes.

```
    post '/chores' do
        authorize
        u = current_user
        new_chore = u.chores.build(task: params[:task])
        if new_chore.save
            redirect '/chores'
        else
            @message = "There was an issue"
            erb :'/chores/new'
        end
    end
		```




