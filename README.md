Android-Uploader-Clickatell
===========================

A variation on the Nightscout Uploader Tool that includes Clickatell Support


FROM README
SMS Uploader Addition for Nightscout Dexcom Uploader
Version 1.2 2014-08-17
Features
  Sends text message directly from upload device using Clickatell SMS subscription
  Can send to one or more cell phones. Smartphone/web are not needed on the listening device.
  This app also sends to Mongo/Azure for web/pebble monitoring (retains Nightscout capability)
  Sends text messages like “BG 110 up 4”, “BG 120 down 7”, or “BG 100 stable”
o  Sends a text message at first reading outside of specified BG range
o  Sends additional messages every X minutes until back in range (configurable)
  You can set min/max BG thresholds to avoid alerting when in range (see “risks” below**)
  If the CGM loses signal and displays no data, sends text message “No data” every 5 min
  If the BG is under 55, sends text message “UNDER 55” every 5 min
Risks
  Consumer grade technology and untested code.  Data may be inaccurate, delayed, or missing.
  Do not use this as your only source of monitoring or for overnight monitoring.
  ** If the CGM uploader is turned off or network connectivity is lost, no texts will be sent even 
though BG may still be out of range.  No text messages DO NOT mean that BG is OK!
Installation and Configuration
1.  Sign up for an account at www.clickatell.com and purchase a API account with US long number 
subscription (the plan is $10/month and includes 500 messages, you can also refill if needed 
mid-month). If your alerts are every 20 minutes for 12 hours/day this may be about $1/day, but 
you can set the frequency of alerts to be whatever you like (see below).
2.  To install the uploader app directly, download only the sms1.2.apk file, email it to your gmail 
account, then log into gmail on your MotoG and open the email. There should be an “install”
button.  – OR – to install from the source code, download the project directory from Dropbox 
save to your PC, then install using Android Studio. 
a.  Launch Android Studio
b.  Import the project
c.  Connect the Moto G
d.  Click “Run” then select the Moto G as the install device when prompted
3.  Connect the Dexcom then start the Nightscout application. 
You should see “CGM+SMS v1.2 Started” if you have installed the application correctly.
4.  Press the 3 dots at the upper right of the app, select preferences, then
a.  Set Clickatell SMS Enabled: ON
b.  Enter your Clickatell username, password, and APID
c.  Enter your Clickatell phone number (1+areacode+7digitnumber, like 16101234567)
d.  Enter recipients separated with commas (like 16101112222,16101113333)
e.  Set the three alert intervals. The number you enter is the multiple of 5 minutes.
f.  Stop and restart the application. You should see messages within a few minutes 
