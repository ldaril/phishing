# Phishing

## Mail analysis 

### Email header

Analyze the **email header** to get the following information
- Sender email address 
- Sender IP address
- Reverse lookup of the sender IP address
- Email subject line
- Recipient email address (this information might be in the CC/BCC field)
- Reply-to email address (if any)
- Date/time

### Email body

The malicious payload is usually a **link** or an **attachment**, so it's interesting to extract all the links from a email, and obtain the attachment safely (in thunderbird, click on save).

We need to:
+ Note the root domain of the links and check the reputation of the URLs and their root domain.
	+  Tools: 
	  + [Talos Reputation Center](https://talosintelligence.com/reputation)
	  + [VirusTotal](https://www.virustotal.com/gui/)
+ Get the checksum from the attachment
```shell
sha256sum <file>
```


#### Info to collect from the email body
- Any URL links (if an URL shortener service was used, then we'll need to obtain the real URL link)
- The name of the attachment
- The hash value of the attachment (hash type MD5 or SHA256, preferably the latter)

**Tools to extract URLs**
+ https://www.convertcsv.com/url-extractor.htm
+ [CyberChef](https://gchq.github.io/CyberChef/)



## Tools

**Tools to analyse email headers**
+ https://toolbox.googleapps.com/apps/messageheader/analyzeheader
+ https://mha.azurewebsites.net
+ https://mailheader.org/

**Tools to get info on sender IP**
+ [https://ipinfo.io/](https://ipinfo.io/)
- whois.domaintools.com
+ whois command line tool

**Tools to get info on an URL without clicking on it yourself**
+ https://urlscan.io/
+ https://www.url2png.com/
+ https://www.wannabrowser.net/
+ https://www.browserling.com/browser-sandbox

**Defang URLs**
+ https://gchq.github.io/CyberChef/

**Tools to create phishing emails**
+ https://webhook.site/