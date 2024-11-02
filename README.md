In this program I iplemented an extended TFTP (Trivial File Transfer Protocol) server and client. The
TFTP server is a file transfer protocol allowing multiple users to upload and download files from the server and
announce when files are added or deleted to the server. The communication between the server and the client(s) is
performed using a binary communication protocol, which support the upload, download, and lookup of files.
The implementation of the server is based on the Thread-Per-Client (TPC) server.
The client uses two threads one thread is reading input from the user keyboard and the other one reads input from the socket.
Keyboardthread reads commands from the keyboard and sends packets to the server defined by the command. Listening thread reads packets from the socket and displays messages or sends packets in return.
The extended TFTP supports various commands for receiving and uploading files.
Upon connecting, a client must specify their username using a Login command. The nickname must be unique and
cannot be changed after it is set. Once the command is sent, the server will reply on the validity of the username.
Once a user is logged in successfully, he can submit commands which deal with file transferring.

Keyboard thread Commands:( Commands that we can type to our terminal and the resulting behavior. We enter the command into the terminal and send it by pressing enter)

LOGRQ
• Login User to the server
• Format: LOGRQ <Username>
DELRQ
• Delete File from the server.
• Format: DELRQ <Filename>
RRQ
• Download file from the server Files folder to current working directory.
• Format: RRQ <Filename>
WRQ,
• Upload File from current working directory to the server.
• Format: WRQ <Filename>
DIRQ
• List all the file names that are in Files folder in the server.
• Format: DIRQ
DISC
• Disconnect (Server remove user from Logged-in list) from the server and close the program.
• Format: DISC

 The extended TFTP supports 10 types of messages: LOGRQ, DELRQ, RRQ/WRQ, DIRQ, DATA, ACK,  BCAST, ERROR, Disc.
 
how to run server and client:

○ Server: from server folder
∎ Build using: mvn compile
∎ Thread per client server:
mvn exec:java -Dexec.mainClass="bgu.spl.net.impl.tftp.TftpServer" -Dexec.args="<port>" 
○ Client: from client folder
∎ Build using: mvn compile
∎ Thread per client server:
mvn exec:java -Dexec.mainClass="bgu.spl.net.impl.tftp.TftpClient" -Dexec.args="<ip> <port>" (use 127.0.0.1 7777)
 
