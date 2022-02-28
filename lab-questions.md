# Lab Questions
The [google doc](https://docs.google.com/document/d/12N2yYORlikxGNZVFl1lPnkZsG-sZ3rRYh3WN0cb1HZI/edit) version

I am giving you some python code that implements a simple echo server.  When a client is connected to the server whatever data it sends will be echoed back to the client.    You will run the code and use netcat (nc) to act as a client, and also change the code to try a few things, see the instructions in the [README](README.md)

## Setup 

Clone this repo on your VM  [P Campbell / Sockets · GitLab](https://gitlab.com/campbe13/sockets-lab/), you may need to install git  and python3.   The general instructions for running the code and connecting to it with netcat (nc) are in the README.md  Make sure you can run the server & connect to it before you go to the next step.
You can run netcat on your windows desktop if you load MobaXterm and start a local terminal.

## Lab exercise

Read the code, note how the socket library calls are used & how the server is implemented. 

Then  follow the actions and answer the questions posed in Instructions & Questions.    

_You may want to take a copy of this file or the google doc and answer the questions in here._

## **Instructions and Questions**

For each of the following run the server(s) as directed, connect to it/them with clients as directed, then answer the question. "talk to it" means use netcat as a client to connect to the port & IP address.   Reminder: external access to your computer will require opening the port on the firewall, as you did for virtual hosts. 

### **connecting to the server**

Run the server in the background:

1. Can you talk to it logged on as another user on the same box? Why or why not?
2. Can you talk to it from another box (your desktop or another VM)? Why or why not?
3. Can you run many instances of the server code in the background? Why or why not?


### **change the port**

Copy the code to server2.py, change the port, choose a port in the range 8000-8999 that you are not using.  

1. Can you run the server code using a different port?  (server2.py) Why or why not?
2. Can you run both ./server.py & and ./server2.py & at the same time, in the background, does it work? Why or why not?
3. Can you talk to each of them, using nc what do you have to change to talk to server2 ?

### **change the IP to 0.0.0.0, change the port**

Copy the code to server3.py, change the IP address to 0.0.0.0, change the port, choose a port in the range 8000-8999 that you are not using.

1. Can you run the server code using 0.0.0.0 ?  Why or why not?
2. Can you run all three ./server.py & and ./server2.py & and ./server3.py & at the same time, in the background, does it work? Why or why not?
3. Can you talk to each of them, using nc and 127.0.0.1 (what do you have to change to talk to server3?)  Why or why not?
4. Can you talk to the server3 from your desktop, using the IP address of your VM? Try the access  with each port. Why or Why not?   (Use nc on MobaXterm local terminal)
5. Ask another student to talk to server3 from their VM, can you connect using the IP address of your VM? Why or Why not?


### **change the IP to your own VM IP, change the port**

Copy the code to server4.py, change the port, choose a port in the range 8000-8999 that you are not using. Change the IP address to the IP address of your VM.

1. Can you run the server code using your IP address? Why or why not?
2. Can you run all four ./server.py & and ./server2.py & and ./server3.py & and ./server4.py & at the same time, in the background, does it work? Why or why not?
3. Can you talk to each of them, using nc and 127.0.0.1 (what do you have to change to talk to server4?) Why or why not?
4. Can you talk to the server from your desktop, using the IP address of your VM? Try the access  with each port. Why or Why not?    (Use nc on MobaXterm local terminal)
5. Ask another student to talk to server4 from their VM, can you connect using the IP address of your VM? Why or Why not?
6. Bonus: What would happen if you used the same port as server3 and your VM's IP address, try to run them at the same time, ex server5.
