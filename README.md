# SIEMonitor
A simple, yet powerful SIEM Lab, done in Parrot OS with Elastic Cloud Integration

Check out the following Medium blog : https://mayillikestotech.medium.com/creating-a-siem-lab-using-elasticagent-and-parrot-os-1881f46030e4

Parrot OS is a flavour of Linux which emphasizes and leans more towards security, as opposed to getting all the tools from scratch through the terminal in other Linux versions.

We will be using Elastic for recording and collecting the logs

Here’s how you do it:
Setting up a Parrot VM:

Download the Parrot Security Edition from their official website, I use VirtualBox for setting up virtual machines, so I found the following documentation on their website, which was quite helpful:

https://parrotsec.org/docs/virtualization/install-parrot-on-virtualbox/

NOTE : Make sure you choose the security edition :)

Once you download it, you should be seeing a file named ‘Parrot-security-6.1_amd64’ or something similar (depends on if you selected AMD64 or ARM) and it will be of Open Virtualization Format Archive(.ova).

Assuming you already have VirtualBox installed in your computer, if you click on it, it will open a window there, like the one shown below:

You can adjust your settings and when you click finish, the installation will take a while and you will be able to see your VM loading like this (They have a cool wallpaper btw) :
Setting up Elastic to get the logs

Create a free account in Elastic Agent in the following link:

After creating an account, click on Add Integrations:

When it navigates to a page like the one shown below, click on ElasticDefend, which is used to monitor activity:

After this, you will be led to a page like the one below, click on Install Elastic Agent:

Select Linux Tar for the installation as we will be using Parrot OS :

Execute the commands in the terminal window of the Parrot OS. I would suggest that you execute them one by one as opposed to executing them altogether, in order to understand what each command does. Also, while executing these commands, make sure you have stable internet connection.

When all these commands have been executed successfully, you should be expecting a result in the terminal like this :

You can check the installation by running “sudo systemctl status elastic-agent.service” or the command below:

If the installation is successful, you should also be getting this confirmation in that page:
Generating and viewing Logs

You can run some basic nmap commands like the ones shown below:

You can look at the logs generated so far in your deployment:
Creating a Dashboard

You can also create a Dashboard for your logs by going to Dashboard > Create Dashboard > Create Visualization

You can choose the parameters on the right by dragging and dropping the attributes on the left side
Creating Rules

You can create rules by clicking on Alert > Create Rule

I created a rule with basic settings, like the one shown below:

So, this concludes my article. If you had followed whatever I have explained here, Kudos! You set up a Parrot OS Virtual Machine, forwarded logs, generated security events and analyzed them through a visualization and creating alerts— you created a SIEM lab!
References:

https://youtu.be/2XLzMb9oZBI?feature=shared
