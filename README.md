# Tips 

------
### Easy Stored XSS & HTML Injection 

* Payload
```
site:target.com inurl:"contact" | inurl:"contact-us" | inurl:"contactus" | inurl:"contcat_us" | inurl:"contact_form" | inurl:"contact-form" 

```
* Fill the form with an HTML Payload in the First Name and with your XSSHunter Payload in Message and send the form

* Wait for a message in your mail with executed Html Payload or your XSSHunter alert for Stored XSS 

----
