TO IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

Created Linux-based virtual servers: mysql server A & mysql client B and connected both ok.

The script asked us to allow connection from the client to the server by adding the client IP address in the inbound security group rules on the server,

I obtained the client IP address using the “ip address show”  command.

To ensure my server was secure, I ran an sql secure security script “sudo mysql_secure_installation”

had issues with  password set up:  Error message:

... Failed! Error: SET PASSWORD has no significance for user 'root'@'localhost' as the authentication method used doesn't store authentication data in the MySQL server. Please consider using ALTER USER instead if you want to change authentication parameters.

<img width="1680" alt="Screenshot 2023-07-12 at 10 57 26" src="https://github.com/tpbabdul/TundeP/assets/135444991/4761a811-f367-4f0a-84a3-119a3ebd6e31">

I did a google search on the above and got some instructions: 

  -  In a new terminal
  -  Terminate the mysql_secure_installation from another terminal using the killall command: sudo killall -9 mysql_secure_installation
  -  Start the mysql client: sudo mysql
    
 Then I ran the following SQL query:
 
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'SetRootPasswordHere'; and
exit

I ran the command to secure it:  sudo mysql_secure_installation

When promoted for the password I entered "password" 


When I tried to create a user to administer the DB:

CREATE USER 'remote_user' @'%' IDENTIFIED WITH mysql_native_password BY 'password';

I got the following error message: (show picture)
ERROR 1396 (HY000): Operation CREATE USER failed for 'remote_user'@'%'

<img width="1680" alt="Screenshot 2023-07-12 at 15 31 26" src="https://github.com/tpbabdul/TundeP/assets/135444991/e37f37ad-d79e-4a8b-9b1b-4443718c9d00">

Did a google search as was directed to drop the user and recreate it:
- drop user 'remote_user';
- flush privileges;
- create user 'remote_user' identified by 'admins_password'

CREATED a test DB:
CREATE DATABASE tundetest_db; (test_db)

Followed script to grant and flushed privileges 

GRANTED privileges

Changed the bind address to allow connection from any device by using 0.0.0.0

I then connected from client Linux Server remotely to server Database Engine without using SSH:

From the client server, I ran “sudo mysql -u remote_user -h  172.31.17.19 -p.

I was successfully connected as I was informed of the “server version”.

<img width="1680" alt="Screenshot 2023-07-12 at 15 53 15" src="https://github.com/tpbabdul/TundeP/assets/135444991/487f203e-73e0-45b8-ad90-02ce7c2255f1">

I ran the command “show databases;” and was successfully shown the two test DBs I created.


<img width="1680" alt="Screenshot 2023-07-12 at 15 55 31" src="https://github.com/tpbabdul/TundeP/assets/135444991/fd100138-8d29-4ace-98da-8a8446d6e42c">
