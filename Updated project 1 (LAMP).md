## WEB STACK IMPLEMENTATION (LAMP STACK) IN AWS

In this project, I deployed an EC2 instance in AWS cloud.  The steps were relatively straighforward to follow, but on the first few attempts I found it difficult to connnect to the instance using the SSH command in ubuntu.  I watched a few online videos and eventually realised the issue was with the private key. Eventually I managed to download the private key and connect.

I also had some minor issues when accessing the public IP address due to the security rules.  In the end, I decided to terminate the instance and create a new one from scratch. 

The rest of the project was relatively straightforward to follow and I began noting some command shortcut down.

I also found out after many attempts that when I need to get back into an instance after I log off, I MUST run the "cd download" command before I am able to connect - I am not sure this is the right way, but as long as it works.!

I ran into some more trouble at the final stage where I had to enable PHP for the website using Apache - I struggled to find the path to save the penultimate command so had to join a blocker session.  The guys were kind and patient in sorting me out.

I however, was unbale to Create a new file named index.php inside your custom web root folder using :vim /var/www/projectlamp/index.php
and then add the file:
<?php
phpinfo();.  This meant that my website didn't show as expected on the last page, but I will check to see what else I may have done differently in my spare time.

The image shows the last failed command.

<img width="1440" alt="Screenshot 2023-06-07 at 22 23 17" src="https://github.com/tpbabdul/Project-One/assets/135444991/b0d16600-1a46-446f-afe8-7e36edd284c7"><img width="1440" alt="Screenshot 2023-06-07 at 22 23 17" src="https://github.com/tpbabdul/Project-One/assets/135444991/8ab1360c-b607-41be-926e-3b9ee8ec1eea">

This meant that my webpage didn't display the information about your server from the perspective of PHP.

Following the blocker session, I was able to create the index.php file and add the php info.  All worked as expected.
