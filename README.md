# Creating SIEM, Connecting Network, and Log Queries
 ## Table of Contents
1. Connecting Our LAN Network
2. Installing and Configuring our SIEM
3. Log Queries

# Connecting Our LAN Network
- Using pfsense as our firewall, we create a local area network using subnet 10.0.0.1/8
- Configuring our local LAN IP through pfsense
![Alt text](<assets/Changing pfsense Ip.png>)
![Alt text](<assets/Configuring LAN ip on pfsense.png>)
![Alt text](<assets/pfsense ip configured correctly w subnet mask.png>)
- Now that our local area network is configured and ready to be connected, we can move over to own VM machines to install splunk enterprise and splunk forwarder.
![Alt text](<assets/ubuntu machine changing static ip.png>)

# Installing and Verifying our SIEM 
- after transferring our installer into our downloads folder, i use the CLI to depackage/install splunk.
![Alt text](<assets/installing splunk.png>)
- Then we initate splunk
![Alt text](<assets/splunk started.png>)
- Using our web interface, we can log into splunk enterprise now
![Alt text](<assets/splunk enterprise login.png>)
- Now heading over to my Windows 10 VM, i begin to install my splunk forwarder
![Alt text](<assets/installing splunk forwarder.png>)
![Alt text](<assets/host machiine is the ubuntu machine.png>)
- Now lets head over into our splunk enterprise settings, and start collecting some data!
- starting off first with adding our forwarder machine from windows 10.
![Alt text](<assets/adding our forwarder.png>)
- Reviewing the configurations, everything checks good
![Alt text](<assets/review of adding splunk forwarder.png>)
- Also sure to make sure configurations are properly working, which they are, we are logging windows 10 info now.
![Alt text](<assets/verifying the logs work to windows.png>)
- Now lets start collecting data from our host machines logs.
![Alt text](<assets/setting up splunk monitoring data.png>)
![Alt text](<assets/we selected to monitor our var logs.png>)
- Now lets verify the our logs are being properly queued.
![Alt text](<assets/var logs log query.png>)
# Log Queries
- lets start with creating a test account.
![Alt text](<assets/creatiing a test account.png>)
![Alt text](<assets/verifying the logs are working properly.png>)
- Now we can start playing with more queries, and operators.
![Alt text](<assets/var log query authentication failure.png>)
- I logged out, and purposely entered the host machines password incorrectly, and splunk logged these.
- scrolling through the log, i clicked on the user to add it into our search.
![Alt text](<assets/adding john doe to log query.png>)
and splunk adds johndoe to the search automatically, a very nice and quick feature.
![Alt text](<assets/showing john doe in log query.png>)
- and to finish off we test out the usage of some operators.
![Alt text](<assets/log query operators.png>)