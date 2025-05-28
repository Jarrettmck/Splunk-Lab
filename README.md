<h1>Splunk Tools</h1>


<h2>Description</h2>
In this Lab, I will be presenting the different ways that Splunk can analyze data and the steps to use the tools that it has to offer.
<br />


<h2>Utilities Used</h2>

- <b>SPLUNK</b> 
- <b>CVE via NIST</b>
- <b>OSINT</b>

<h2>Environments Used </h2>

- <b>Linux OS/VM</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Go to Search and Reporting and input the query or URL of the scanned incident. <br/>
  <br />
<img src="Screenshot 2025-05-22 161347.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Look through the Sourcetypes used:  <br/>
<img src="Screenshot 2025-05-22 161552.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Find the source IP with the highest data usage for that source type: <br/>
<img src="Screenshot 2025-05-22 161658.png" alt="Disk Sanitization Steps"/>
<br />
<br />
Find the CVE Value of the Alert through NIST which shows you the decription, solutions, and tools for the alert. (fromm Alert Signature)  <br/>
<img src="Screenshot 2025-05-22 162008.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="Screenshot 2025-05-22 162145.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Track down the IP responsible by following up in the search bar with IP and show the raw text. You can also show and print your findings in chart form by going to statistics, then to visualization. <br/>
<img src="Screenshot 2025-05-22 164356.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
With finding that IP you can type http_method=POST to see the post request percentage:  <br/>
<img src="Screenshot 2025-05-22 165527.png"80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use |table_time uri src_ip dest_ip form_data to create a table containing important fields. To only show username and password data that the attacker used add- form_data=*username*passwd*:  <br/>
<img src="Screenshot 2025-05-22 170222.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
For regex or rex, use input rex field=form_data"password=(?<creds>\wt) to extract password values only used by the attacker:<br/>>
<br />
<img src="Screenshot 2025-05-22 172134.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
