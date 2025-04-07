1. What is inside a packet?

    **All packets have a header, which stores the address of where to send the packet and a payload which stores the data or message of the packet.**

2. What is the purpose of an internet layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?

    **The purpose of an internet layer is to inter-connect networks. As a client, the way that networks inter connect with each other and the way that computers are identified via ip address, must be specified in the protocol.**

3. What is the purpose of the transport layer in the TCP/IP protocol? What do you, as a client, need to specify in this protocol?

    **The purpose of the transport layer is to provide an abstraction for the process of sending and receiving data, to appear as if they are communicating directly with each other. It can also provide a mechanism, called ports, to differientiate communication destined for one process versus another.**

4. What is the difference between SMTP and HTTP?

    **SMTP is used to transmit email messages and HTTP is used to download web content.**

5. What is the difference between an IP address and a domain name? 

    **An IP address is a 4-byte/32-bit number in Version 4 of TCP/IP protocol while a domain name is a hostname to identify a networked device which requires IP addresses.It's harder to remember an IP address but it's easier to remember a domain name.**

6. How does the operating system use ports?

    **The port addresss is used to deliver the packets on the computer to the right process. And the port address is a way for the Operating System to divide up the data arriving from the network based on the destination process.**

7. Write code that creates a socket connection to ip address 123.45.678.900 at port 4040. Then, print a color to that socket’s output.

    ````
    import java.util.*;
    import java.net.*;
    import java.io.*;

    public class HelloSocket{

        public static void main(String args[]){

            Socket sock=null;        
            try{
            sock = new Socket("123.45.678.900",4040);
            }catch(Exception e){
                System.err.println("Cannot Connect");
                System.exit(1);
            }

            try{
                PrintWriter pw = new PrintWriter(sock.getOutputStream());
                pw.println("blue");
                pw.close(); //close the stream
                sock.close();//close the socket
            }catch(Exception e){
                System.err.print("IOException");
                System.exit(1);
            }

        }
    }
    ````

8. What is the difference between a socket’s input stream and its output stream? 

    **The input stream reads the data from the connection while the output stream writes the data to the connection.**

9. What is the difference between a Socket and a SocketServer?

    **Sockets are used as a client socket in a 2-way communication with a server. So, the socket is connected to the server as a ipaddress/host and port. SocketServers are similar to sockets but it requires an additional step of needing to accept the incoming connect.**

10. How are threads useful with servers? How does a server manage to always be listening for sockets trying to connect?

    **Threads are useful with servers because it allows server to handle multiple client requests at once. A threaded socket server starts a new thread for each thread so that the main thread can continue to listen to incoming connections.**