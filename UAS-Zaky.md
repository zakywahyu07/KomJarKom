# Question below are based on the trace file tcp-ethereal-trace-1 in in http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces.zip
## Answer the following questions for the TCP segments:
1. What is the IP address and TCP port number used by your client computer (source) to transfer the file to gaia.cs.umass.edu?
2. What does gaia.cs.umass.edu use the IP address and port number to receive the file. (Attach the screenshot of your Wireshark's display)
3. What is the sequence number of the TCP SYN segment that is used to initiate the TCP connection between the client computer and gaia.cs.umass.edu? What is it in the segment that identifies the segment as a SYN segment? (Attach the screenshot of your Wireshark's display)
4. What is the sequence number of the SYN ACK segment sent by gaia.cs.umass.edu to the client computer in reply to the SYN? What is the value of the ACKnowledgement field in the SYNACK segment? How did gaia.cs.umass.edu determine that value? What is it in the segment that identifies the segment as a SYNACK segment? (Attach the screenshot of your Wireshark's display)
5. What is the sequence number of the TCP segment containing the HTTP POST command? Note that in order to find the POST command, you’ll need to dig into the packet content field at the bottom of the Wireshark window, looking for a segment with a “POST” within its DATA field.(Attach the screenshot of your Wireshark's display)
6. Consider the TCP segment containing the HTTP POST as the first segment in the TCP connection. What are the sequence numbers of the first six TCP connection segments (including the HTTP POST segment)? At what time was each segment sent? When was the ACK for each segment received? Given the difference between when each TCP segment was sent, and when its acknowledgement was received, what is the RTT value for each of the six segments? What is the EstimatedRTT value (see page 237 in textbook) after the receipt of each ACK? Assume that the value of the EstimatedRTT is equal to the measured RTT for the first segment, and then is computed using the EstimatedRTT equation on page 237 for all subsequent segments. (30%)
Note: Wireshark has a nice feature that allows you to plot the RTT for each of the TCP segments sent. Select a TCP segment in the “listing of captured packets” window that is being sent from the client to the gaia.cs.umass.edu server. Then select: Statistics->TCP Stream Graph->Round Trip Time Graph.
7. What is the length of each of the first six TCP segments?(Attach the screenshot of your Wireshark's display)

# Answer
1. Client Computer (source) IP address: 192.168.18.30 TCP port number: 55551
![image](https://github.com/user-attachments/assets/261c4ea5-1de0-4b88-b48b-0d7f44937f2f)

2. Server (source) IP address: 128.119.245.12 TCP port number: 443
   ![image](https://github.com/user-attachments/assets/7bab85e6-516c-4ef7-8b75-89651abb14a4)

3. The sequence number of the TCP SYN segment used to initiate the connection between the client computer and gaia.cs.umass.edu is 0. This segment is identified as a SYN segment because the SYN flag is set, as indicated in the header details with the information Flags: 0x002 (SYN).
  ![image](https://github.com/user-attachments/assets/48da01d7-c33d-49b2-ba5d-460d99a7ac51)

4. The SYN-ACK segment sent by gaia.cs.umass.edu to the client has a sequence number of 0, as shown in the segment details with [Seq=0]. The acknowledgment field in this segment is set to 1, calculated by adding 1 to the sequence number of the SYN segment received from the client (0 + 1 = 1). This segment is recognized as a SYN-ACK because both the SYN and ACK flags are enabled, as indicated in the header information.
![image](https://github.com/user-attachments/assets/794092be-6511-4c5e-94f7-07c8d9a88e5d)

5. The sequence number of the TCP segment containing the HTTP POST command is 633, as shown in the segment details in the Sequence Number section: 633. This segment has a source of 192.168.1.8 and a destination of 128.119.245.12 with the HTTP protocol.
  ![image](https://github.com/user-attachments/assets/172cdf8d-bff5-496c-a8c6-baccc412419c)

6. 2 Reassembled TCP Segments (850 bytes) : #21 (632), #22 (218)
  ![image](https://github.com/user-attachments/assets/c761afe1-849a-4022-a610-ccca8b5d25be)

7. ![image](https://github.com/user-attachments/assets/9b138f99-9a05-400a-8b9c-3465a4aad83b)
