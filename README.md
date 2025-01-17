# Credential Harvesting While Using Site Cloning
<h2>Description</h2>
The Credential Harvesting Lab requires the use of a Kali Linux virtual machine that walks the user through on how to gather or "harvest" sensitive information on a targeted website.
<br />


<h2>Languages and Utilities Used</h2>
<ul><!-- start of main list-->
<li>Terminal</li> 
<li>ifconfig</li>
<li>Social-Engineer Toolkit (SET)</li>
<ul><!-- start of nested list -->
 <li>sudo setoolkit</li>
</ul><!--end of nested list-->
</li>
</ul><!--end of main list -->

<h2>Environments Used </h2>

- <b>Kali Linux</b>

<h2>Lab walk-through:</h2>

<p align="center">
<h3>Step 1</h3><br/>
Boot up Kali Linux virtual machine and login to virtual machine. After logging into Kali Linux virtual machine, open a terminal command window and start the Social Engineering Toolkit (SET) utility by typing the following command in the terminal: <br />
<br />
<b><i>sudo setoolkit</i></b><br /><br />
Select "Update SET configuration" option to refresh SET utility before proceeding to step 2.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/8c669824b6e22f88087ea63d9b660da6f8a0b254/Images/SudoSetoolkit.png" height="50%" width="50%"/><br />
<h3>Step 2</h3><br/>
From the SET menu, choose the "Social Engineering Attacks" option.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/8c669824b6e22f88087ea63d9b660da6f8a0b254/Images/Social%20Engineering%20Attacks.png" height="50%" width="50%"/><br />
<h3>Step 3</h3><br/>
From the social engineering attack vector list of options. Choose the "Website Attack Vectors" option.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/8c669824b6e22f88087ea63d9b660da6f8a0b254/Images/Website%20Attack%20Vectors.png" height="50%" width="50%"/>
<h3>Step 4</h3><br/>
From the website attack vectors list of options. Choose the "Credential Harvester Attack Method" option.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/8c669824b6e22f88087ea63d9b660da6f8a0b254/Images/Credential%20Harvester%20Attack%20Method.png" height="50%" width="50%"/>
<h3>Step 5</h3><br/>
The next menu will ask for a method to harvest a victim's credentials. Choose the "Site Cloner" option since we will be cloning a legitimate site.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/8c669824b6e22f88087ea63d9b660da6f8a0b254/Images/Site%20Cloner.png" height="50%" width="50%"/>
<h3>Step 6</h3><br/>
The SET utility will ask for a local IP address so that it can send POST requests from the cloned website back to the virtual machine. For the purpose of this lab, enter in your Kali virtual machine's local IP address. The local IP address can be found by running the <b><i>ifconfig</i></b> command in a new terminal window.<br /><br />
For the "Enter the URL to clone" field, you can enter in any website that has a sign-in box. For the purpose of this lab, we used https://www.facebook.com<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/8c669824b6e22f88087ea63d9b660da6f8a0b254/Images/Site%20Cloner%202.png" height="50%" width="50%"/>
<h3>Step 7</h3><br/>
Once the URL is entered in, the SET utility will clone the targeted website and display all POST requests of the site back to this terminal. The next step will go into navigating to the cloned website.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/e58acb763b7c99b067bcec046dd0a09bd2406c2f/Images/Site%20Cloner%203.png" height="85%" width="85%"/>
<h3>Step 8</h3><br/>
To get to the cloned website, open a web browser program (such as Mozilla Firefox or Google Chrome) in your Kali Linux virtual machine and enter in your local IP address into the browser. <br /><br />
You will be able to view the cloned login page for the targeted website (in this case would be Facebook). Enter a random username and password into the username and password field then press "Log In."<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/e58acb763b7c99b067bcec046dd0a09bd2406c2f/Images/Cloned%20Website.png" height="85%" width="85%"/>
<h3>Step 9</h3><br/>
Go back to the terminal where the SET utility is running in the background. You will start to see lots of text from the numerous POST requests being sent from the cloned website. Scroll down until you see the lines "POSSIBLE USERNAME FIELD FOUND" & "POSSIBLE PASSWORD FIELD FOUND" in the output. <br /><br />
You should now be able to see the username and password you entered on the cloned site in cleartext. <br /><br />
NOTE: If you do not see the username and password in cleartext, this will indicate the site code has been patched to prevent credential harvesting. Facebook's site appears to have patched the site code that would prevent the credential harvesting tool from working.<br /><br />
<img src="https://github.com/AndrewLSimmons/CredentialHarvestingLab/blob/e58acb763b7c99b067bcec046dd0a09bd2406c2f/Images/Credential%20Harvester%20Output.png" height="85%" width="85%"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
