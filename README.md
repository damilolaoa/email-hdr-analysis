<h1>Email Header Analysis</h1>

<h2>Description</h2>
This project shows how I conduct an email header analysis on one of the emails in my inbox. I will be using a tool called MX Analyzer to determine the authenticity of the email.
<br />

<h2>Utilities Used</h2>
- <b>Gmail</b> <br/>
- <b>MX Analyzer</b>

<h2>Environments Used </h2>
- <b>Kali Linux</b>

<h2>Acronyms Used </h2>
- <b>SPF: Sender Policy Framework</b> <br/>
- <b>DKIM: DomainKeys Identified Mail</b> <br/>
- <b>MX: Mail Exchange</b> <br/>

<h2>Lab walk-through:</h2>
This analysis is being conducted via my Linux VM :)

<p align="center">
  <b>The sample email I'll be using: </b> <br/>
<img src="https://imgur.com/SldPl5C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
First, I click on the 3 dots to the far right of the email and click show original:  <br/>
<img src="https://imgur.com/hDF2aSq.png" height="80%" width="80%" alt="Email Header Analysis Steps"/>
<br />
<br />
This page shows details about the email. The sender and return-path should be the same, and the "To" field should contain my email address, but it doesn't :) :  <br/>
<img src="https://imgur.com/wuxv2eP.png" height="80%" width="80%" alt="Email Header Analysis Steps"/>
<br />
<br />
To analyze the entire email without clicking on things that'll make me vulnerable, I click "Copy to Clipboard" and go to the MX Analyzer website. I make sure to be on the "Analyze Headers" tab so that I can paste the copied information in the box, and then I click the Analyze Header button:  <br/>
<img src="https://imgur.com/0xnhH2p.png" height="80%" width="80%" alt="Email Header Analysis Steps"/>
<br />
<br />
As expected, everything in here screams red flag. SPF helps protect senders and recipients from spam, spoofing, and phishing, while DKIM is a form of email authentication that also helps with non-repudiation. From the screenshot, we see that SPF and DKIM could not clear this email as non-malicious based on their features:  <br/>
<img src="https://imgur.com/azjTw4D.png" height="80%" width="80%" alt="Email Header Analysis Steps"/>
<br />
<br />
Scrolling down the page, we also see that the Sender and To fields have almost the same element (dammilolang), implying that I sent this to myself. In the To field specifically, the domain is @aol.com which is wrong. Additionally, in the From field, the email address doesn't look legitimate. That raises another red flag for me:  <br/>
<img src="https://imgur.com/dQzI905.png" height="80%" width="80%" alt="Email Header Analysis Steps"/>
<br />
<br />
  <b>In closing: </b> Essentially, the analyzing tool is just one of many that helps identify if an email is truly malicious. This allows for extra caution on the enterprise level, while catiching the malicious emails that slip through the cracks. 
</p>
