---
layout: post
title:      "Regular Flash vs. flash.now"
date:       2020-03-04 04:11:53 +0000
permalink:  regular_flash_vs_flash_now
---


I did not understand how flash worked and then someone showed me the magic, it was like fireworks in my head.  The ease of being able to display any type of message when an object is trying to pass or fails gives the user a message.  I used a flash message for the create and edit methods, I wanted my users to know whether their account was able to be created or if it had failed.  I noticed a bug when a user was created and I went back one page, I wanted the flash message to disappear so I learned about the flash.now

```
      flash.now[:danger] = "Appointment could not be made."
```

flash.now allows the message to used just for the current message but I had to make sure that I used render vs redirecting to make sure it worked.  If my create method fails to save the student and I render a new template, its not going to result in a new student but I still want to display my flash message I need to use flash.now


```
   def create
        @student = Student.find(params[:student_id])
        @appointment = current_student.appointments.new(appointment_params)
        if @appointment.save
            flash[:success]= "Appointment created"
            redirect_to student_path(@student)
        else
            flash.now[:danger] = "Appointment could not be made."
            render :new
        end
    end
```


In the example below I created a method that will iterate through a hash of what I wanted my flash to display.  

```
      <% flash.each do |message_type, message| %>
        <div class="alert alert-<%= message_type %>"><%= message %></div>
      <% end %>
```


I kept it nice and simple, used a bootstrap route with the [:success] and [:alert] when I had a failure.

```
flash[:danger] = "You do not have access to delete others appointments"
```

```
flash[:success] = 'Appointment updated'
```


