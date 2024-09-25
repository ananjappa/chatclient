# Chat Client


Created a chat client that is able to communicate with a server. 
The client will send messages to the server, which is then able to
broadcast the message to all the other clients on the system. Similarly, the
client will be able to receive messages directly from the server, thus enabling
the user to read messages sent by all other clients on the system. 


You will be hosting your server on this IP address: 127.0.0.1 which will listen and wait for connections on a port. 

This program requires two command-line arguments: server IP and port. If no
arguments have been supplied, the usage message prints
to stderr and returns `EXIT_FAILURE`.

    "Usage: %s <server IP> <port>\n"

The IPv4 address is written in dot-decimal notation: a.b.c.d, where
a, b, c, and d can be any integer 0 through 255. If you are running the server
locally, you specify the address as 127.0.0.1.

The port must be an integer the range [1024, 65535]. 

After parsing the command-line arguments, the program prompts the user for a username.
If the length of the username is 0, the program reprompts. The same holds if it
is too long, in which case the program outputs

    "Sorry, limit your username to %d characters.\n"

where %d is `MAX_NAME_LEN` and then reprompts the user.



1. `STDIN_FILENO`

    If a message is too long s.t. no new line character is found before visiting MAX_MSG_LEN characters, 
    standard error prints:

        "Sorry, limit your message to 1 line of at most %d characters.\n"
    
    where %d is `MAX_MSG_LEN`. Consume the rest of the characters up to EOF or a new line character, so that
    message is discarded.

    Then, if the message is equal to "bye", print "Goodbye.\n" client is shut down.