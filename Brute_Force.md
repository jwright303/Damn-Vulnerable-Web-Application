The login functionality normally works by having users enter their username and password into the site. 
If the proper credentials are entered then the user is welcomed to the site, otherwise, an error message is given telling them the username and password are not recognized.

To exercise this vulnerability you need to have a username list and password list as well as a program to automate the login attempts. 
The program then iterates through the usernames and passwords and checks them against the site. 
All the user will have to do is look at the difference in the response message from the site (Incorrect user name versus a welcome message). 

It’s not necessarily that the feature worked differently than normal use, rather the feature didn’t prevent malicious use. 
In fact, the problem is that the feature worked as normal for all the attempts which allow malicious users to test out a lot of different combinations to find a valid username and password combination

This vulnerability is really important because if malicious users can access other accounts then they can do a lot of damage. 
They could view the personal information of the account they logged into, or make changes to their account. 
Similarly, since they guessed the password they could change it so that the real user can’t log in to their account. 
Furthermore, since we were able to get access to the admin account, we could potentially make significant changes to the site, including injecting malware, or a keylogger to steal other information.

To fix the vulnerability there could be a timeout function that locks an account for a fixed amount of time after too many login attempts. 
Similarly, for the case of the attack I used, special precautions could be made to give a similar message for successful and unsuccessful attempts (more on that later). 
I found some of these countermeasures by switching to the impossible security mode and using the same method.  
Source:https://owasp.org/www-community/attacks/Brute_force_attack


Notes: The process started by gathering the cookie information and URL from the session on the site. 
Then a password list was created (I made it myself using some random password and the one I knew was on there, but longer ones exist for this).
Finally, I ran the wfuzz algorithm supplying the cookie information, password list, and URL. This printed out the response page for each session. 
I used the difference in word count to identify the correct password. 
