# Module 9 Labs: Explaining Network Security Concepts
## Lab 9.1: Create a Honeypot
Complete this lab as follows: <br>
### Use Pentbox to create a honeypot on www_stage.
From the Favorites bar, select Terminal. <br>
At the prompt, type cd pentbox-1.8 and press Enter to change to the pentbox directory. <br>
Type ./pentbox.rb and press Enter to start Pentbox. <br>
Type 2 and press Enter to select Network Tools. <br>
Type 3 and press Enter to select Honeypot. <br>
Type 1 and press Enter to select Fast Auto Configuration. <br>
### From the Analyst-Lap computer, test the honeypot using Google Chrome.
From the top navigation tabs, select Buildings. <br>
Under Blue Cell, select Analyst-Lap. <br>
From the taskbar, select Google Chrome. <br>
In the URL field, enter www_stage.corpnet.xyz and press Enter. <br>
In the top right, select Questions. <br>
Answer Question 1. <br>
Minimize the Lab Questions dialog. <br>
### Review the effects of the intrusion on www_stage.
From the top navigation tabs, select Buildings. <br>
Under Building A, select Basement. <br>
Under Basement, select www_stage. <br>
&emsp; Notice the INTRUSION ATTEMPT DETECTED message at the bottom of the Pentbox window. <br>
### Answer the questions.
In the top right, select Questions. <br>
Answer Question 2. <br>
## Lab 9.2: Analyze a DoS Attack
Complete this lab as follows: <br>
### Using Wireshark, capture packets on the enp2s0 interface.
From the Favorites bar, select Wireshark. <br>
Under Capture, select enp2s0. <br>
Select the blue fin to begin a Wireshark capture. <br>
### Using a Terminal, ping CorpTest (192.168.10.19).
From the Favorites bar, select Terminal. <br>
At the prompt, type ping CorpTest (or 192.168.10.19) and press Enter. <br>
In Wireshark, apply a display filter by typing icmp (lower case). Note the packets captured in Wireshark. <br>
After a few seconds, type Ctrl-C to stop the ping. Clear the display filter. <br>
### Filter the packet capture to show only SYN packets, then start a SYN flood.
In Wireshare's Apply a display filter field, type tcp.flags.syn==1 and press Enter. <br>
From the Terminal, type hping3 --syn --flood CorpTest (or 192.168.10.19) and press Enter to start a TCP SYN flood against the CorpTest server. <br>
After a few seconds of capturing packets, select the red box to stop the Wireshark capture. <br>
### Examine the captured packets and answer the question.
Maximize the Wireshark window for better viewing. <br>
In the top pane of Wireshark, select one of the packets captured with a destination address of 192.168.10.19. <br>
In the middle pane of Wireshark, expand Transmission Control Protocol. <br>
Scroll down to Flags. <br>
&emsp; Notice that the Flags item in this pane and the data in the Info column in the top pane show that this (and all the packets) is a SYN packet. <br>
In the top right, select Questions. <br>
Answer the question. <br>
## Lab 9.3: Analyze a DDoS Attack
Complete this lab as follows: <br>
### Use Wireshark to capture packets and filter for packets with the SYN flag set.
From the Favorites bar, select Wireshark. <br>
Under Capture, select enp2s0. <br>
From the menu, select the blue fin to begin the capture. <br>
In the Apply a display filter field, type tcp.flags.syn==1 and tcp.flags.ack==0 and press Enter to filter the Wireshark display to show packets with only the SYN flag. <br>
&emsp; Notice that there is a flood of SYN packets being sent to 198.28.1.1 (www.corpnet.xyz). <br>
### Use a filter to display only packets that have the SYN flag and the ACK flag set.
In the Apply a display filter field, change the ending of the tcp.flags.ack portion from a 0 to a 1 and press Enter to filter the Wireshark display to only those packets with both the SYN flag and ACK flag. <br>
&emsp; You should notice that there are far fewer SYN-ACK packets than SYN packets. The server is so busy that it can't respond to all of the packets.
Select the red square to stop the capture. <br>
### Use a filter only to display packets that contain the ACK flag and answer the question.
In the Apply a display filter field, change the ending of the tcp.flags.syn portion from a 1 to a 0 and press Enter to filter the Wireshark display to packets with only the ACK flag. <br>
&emsp; You should see ACK packets, but none of them are being sent to 198.28.1.1 (www.corpnet.xyz). In a SYN attack, the ACK packets are never sent so that it ties up the half-open connections on the server. <br>
In the top right, select Questions. <br>
Answer the question. <br>