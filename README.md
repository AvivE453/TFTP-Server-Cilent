In this program I iplemented an extended TFTP (Trivial File Transfer Protocol) server and client. The
TFTP server is a file transfer protocol allowing multiple users to upload and download files from the server and
announce when files are added or deleted to the server. The communication between the server and the client(s) is
performed using a binary communication protocol, which support the upload, download, and lookup of files.
The implementation of the server is based on the Thread-Per-Client (TPC) server.
The client uses two threads one thread is reading input from the user keyboard and the other one reads input from the socket.
Keyboardthread reads commands from the keyboard and sends packets to the server defined by the command. Listening thread reads packets from the socket and displays messages or sends packets in return.
