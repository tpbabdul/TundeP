AWS MERN WEB STACK IMPLEMENTATION 

Project shows how to implement a web solution on MERN stack in AWS Cloud

I created an EC2 instance, MongoDB account and Postman account

I followed the script as explained so the connection was successful and connected to EC2

<img width="1680" alt="Screenshot 2023-07-07 at 10 26 26" src="https://github.com/tpbabdul/TundeP/assets/135444991/aed13d0a-65b8-4132-b74d-afc043c69925">


up until when i tried to update the index.js to reflect the use of .env so that Node.js can connect to the database. 

I started getting various error messages as the server failed to start many times so I kept going back to the script to check for errors

![image](https://github.com/tpbabdul/TundeP/assets/135444991/06e6d475-11c3-4dd5-a365-006f8ff396fb)


I also had some issues getting the right path to getting the DB username, password and DB.  The instructions were not easy to follow.  It took me a few hours to eventually get the right path.

Eventually, I got an error message indicating the port :5000 was already in use so I searched on google for the possible causes of it.

I googled the error and discovered the port :5000 had to be terminated using:

lsof -i tcp:5000 (to find the node id &
kill -9 *node no* e.g kill -9 32006

Once that was done, I was able to connect to node .index.js succesfully.


<img width="1680" alt="Screenshot 2023-07-07 at 16 09 35" src="https://github.com/tpbabdul/TundeP/assets/135444991/407e95ce-1a55-45fc-abcc-ba86f5821309">


I progressed to connecting to postman:

The first code ran in postman:  created a POST request to the A post to the API
the code i wrote returned: Welcome to express, but the status 200 ok was displayed.  Is that the expected behaviour?
same thing happened in GET  (APIS not working correctly)

<img width="1680" alt="Screenshot 2023-07-07 at 16 31 33" src="https://github.com/tpbabdul/TundeP/assets/135444991/9719b2fe-6403-4240-acfd-b449c7d8d265">


I progressed to the front-end creation despite the above

It was pretty straighforward following the script, but then I experienced some issues when I added the key value pair in the package.json file "proxy": "http://localhost:5000".

when I ran the "npm run dev" command, the applicatipon did not start running on localhost:3000

I tried on 2 other occasions to attempt the rest of the project but the errors kept occuring so I stopped.
