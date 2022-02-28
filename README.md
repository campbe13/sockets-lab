# code for creating sockets
For teaching/learning about sockets, playing with the underlying TCP transport layer communications.  TCP is the transport used for a lot of application layer protocols. 


If you would like to try this you will need to install (or check for)
1.  [Python V 3 (preferred)](https://www.python.org/downloads/)   `python3 --version`  or `python --version`
1.  netcat `nc`  on *nix

#  echo server
see [server.py](server.py) when you run the server the process logs to socket.log (it appends, does not overwrite so you may want to delete old versions as needed)
## server side
Run the server code, it will bind to tcp (stream) & ip & port
* run in background `./server.py &`
   * binds to 127.0.0.1:8111
   * check it with `netstat -lan |less`  note the state LISTEN
   * if it crashes or has just ended the ip&port may still be bound, in a TIME_WAIT status instead of LISTEN,
     you can see this through netstat, you will have to wa,it for it to end
   * you can see the comms via socket.log in the cwd
## client side, talk to server
On the same system, use netcat (nc) to act as a client & make the socket pair
* fake out client comms with netcat 
   * talk to the server `nc -v -n 127.0.0.1 8111`
   * it will echo the data you type in back at you, as long as the socket pair is live
   * `quit` will end the connection  on the server side
   * you will have to hit enter again after entering quit as that will signal nc to stop
   * check the socket source & dest while you are talking to the server `netstat -lan|less` and after you quit (you may see TIME_WAIT)
## Use the code in a lab exercise 
Follow the instructions in [lab-questions](lab-questions.md) to play with and learn about TCP sockets.
## Teacher's version in
[restricted, gitlab](https://gitlab.com/dawsoncollege/infra-linux2-440/-/tree/master/sockets)
