---
layout: essay
type: essay
title: "Checkpoint assignment 3"
# All dates must be YYYY-MM-DD format!
date: 2023-12-12
published: true
labels:
  - Progress
---

### My Progress in Programming
###### My programming skills have greatly improved in the following ways:
I have improved my understanding of where programming languages such as JavaScript can be implemented in a useful way. I have greatly improved my way of thinking about a website and how it is buildt up. I have improved my code setup by commenting and implementing things in a useful and general way. 

The link to my screencast is here: https://youtu.be/HQXu6mWoxss 

#### Describe your design for your site’s shopping cart. 
My shopping cart will be a separate page where the user can add and remove products, and the products are retrieved from the users session. The cart can be accessed at all time, even when no products are selected (an error message will show), and when the user is not logged in. However, to get to the invoice, the user must be logged in. 

#### Explain specifically how you will use sessions to manage your shopping cart. In particular, what shopping cart data will be stored in the session, what data format will be used (NOT what data type, but the format like with the data format used for your registration data). Use code examples showing what data structures (such as arrays and their objects) you will use to manage the shopping cart data and how they will be used in a session.
The data format used is an object within an object, organized by product type, where each product type has an associated object storing quantities for each product. This structure allows me to easily manage and retrieve shopping cart data for different product types. 
shopping_cart={Bags: {…}, Towels: {…}, Hats: {…}}

#### How will you avoid access to your application when the user has not logged in or registered? What are the particular security concerns you must address?
User is authenticated before allowing access to sensitive parts of application (invoice) by using cookie. I am managing security concerns by: 
Prevent client-side script access to session (`httpOnly`)
Have expiration for session and cookies
No information is stored in the qstr, and only name and email is stored in cookie

#### Upon a successful login, how do you provide personalization in your UI? Explain how you did or will do this (paste code if necessary)
User name and email is displayed on products_display when logged in, retrieved from cookie. 
Example:
            // Extract and parse the 'name' cookie
            const cookieName = document.cookie.split('; ').find(row => row.startsWith('name='));
            const userName = cookieName ? decodeURIComponent(cookieName.split('=')[1]) : null;

            // Update the welcome message based on whether the user is logged in
            const welcomeMessage = document.getElementById('welcomeMessage');
            if (userName) {
                welcomeMessage.innerText = `WELCOME, ${userName.toUpperCase()}`;
            } else {
                welcomeMessage.innerText = 'WELCOME';
            }

#### How are you approaching Assignment 3 differently than Assignment 2?
I am writing a checklist for everything that needs to be done, and check off when the task is completed. I am also using the debugger more frequently. 
