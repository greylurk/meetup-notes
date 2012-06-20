Katherine Jamul @kjam
VP at Pop-Up Pantry

Django at Washington Post

Simple Facebook Auth in Django

 * More and more users are continuously logged in FB
 * Easy to Integrate with your own profile,
 * Easier than building a full Facebook App

Chose django_facebook_oauth (Ryan Mark's Fork)

Why? I only needed/wanted Auth at this point. 
 * Posting to wall might happen, but just keep it simple for now.

 1. Pip install 
 2. Add or tewak some settings
 3. Run syncdb
 4. Run runserver

It just works, but how? 

Three-legged oauth
Get info back from FB including email, first and last name, profile photo, etc.
Updates access token if found, otherwise find an existing user

http://github.com/ryanmark

Use the fork(2)
===============

What is a Process? 
 - The "atom" of Unix
 - Processes have names and IDs
 - Processes can fork


