---
layout: post
title:      "To Render or not to Render, that is the Question"
date:       2018-10-15 16:44:30 +0000
permalink:  to_render_or_not_to_render_that_is_the_question
---


Rendering and Redirects are topics that confuse beginner programmers, so I decided to write a blog post to help clarify the key differences.  
In Sinatra, render tells it which view to present to a user while retaining access to any variables defined in that controller. Redirect tells your browser to send a request to another URL.  The view you redirect to does not have access to any variables defined in the controller. In the case of render, all the information stored in params is preserved; therefore a user can edit the information in a form, for example, and resubmit. 

post '/signup' do
        
         @user = User.new(:username => params[:username], :email => params[:email], :password => params[:password])
          if @user.valid?
            @user.save
            session[:user_id] = @user.id
    

            redirect to "/users/#{@user.id}"
          else 
            erb :'users/create_user'
          
        end
      End


In the above code, both redirect_to and render are referenced. Redirect_to is used in the IF statement because variables are not needed to load the pages. @user.id is interpolated purely, so the browser knows what page to load. The else renders because we want to keep the information that exists in params. Rendering keeps the form filled in. Wouldn’t you hate to have to redo a long form? 

To conclude, if you want a user to have access to the variables you defined in the controller, render. Redirect sends a request to the browser without retaining access to any variables. 
