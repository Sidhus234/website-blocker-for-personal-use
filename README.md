<h1>Website Blocker</h1>

The python script will run as soon as your PC starts, and canhelp block certain websites during certain hours. For example - we could block social media sites during the working hours.

Windows, Mac and Linux have /etc/hosts file which can be used to block access to certain websites. For example in windows, the hosts file can be found here (C:\Windows\System32\drivers\etc\hosts).

We will open this file using Python and add websites to be blocked. For example the said program will write the blocked social media websites to this hosts file from 8 AM to 6:30 PM based on local time of PC.

Host file can only be modified by administrator of the PC. Hence, we need to open the windows terminal as admin to run this file.

<h2><a id="index">Index</a></h2>

[1. Scheduling Python Script as Admin on Windows Machine](#schedulepythonscript)<br>
[2. Scheduling Python Script on Linux/Mac OS](#schedulescriptlinux)<br>

<h2><a id="schedulepythonscript">1. Scheduling Python Script as Admin on Windows Machine</a></h2>
<ol>
<li>Change the python extension to .pyw instead of .py (this will allow the python file to run in the background).</li>
<li>Open Task Scheduler and Create a new task. Task Name: "Website Blocker".</li>
<li>Select Configure for: "Windows 10" or whatever version of windows you are using.</li>
<li>Also select "Run with highest privileges". This will ensure that if you have admin rights, the task will run with admin rights.</li>
<li>The click on "triggers" and "New". Begin the task: "On Startup".</li>
<li>Then click on "Actions" and "New". Action would be "Start a Program". Browse and select the python script. </li>
<li>Go to "Conditions" and uncheck the option under "Power", "Start the task only if the computer is on AC Power". We want our program to run even when we are on battery.</li>
<li>After all above settings, click "Ok".</li>
</ol>

<h2><a id="schedulescriptlinux">2. Scheduling Python Script on Linux/Mac OS</a></h2>
<ol>
<li>Open Terminal, launch Visual Studio and change host path to "/etc/hosts"</li>
<li>Type command "sudo python3 website_blocker.py" and click Enter. The program should work.</li>
<li>Open crontab using command "sudo crontab -e" in terminal.</li>
<li>Add this line "@reboot python3 {filepath}/website_blocker.py" to the crontab.</li>
</ol>