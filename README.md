# CS 2660 Lab Three
### Michael Piscione

-----------------------

### HTML Changes

I identified the vulnerability as the un-hashed JavaScript code at "https://jreddy1.w3.uvm.edu/getStock.js". This file
seems to control the CatCoin stock price displayed while simultaneously allowing for the cross-site scripting
attack via the CDN. To mitigate this attack, I hashed the file using sha256 as the hashing algorithm via the service
provided on srihash.org. Sha384 and Sha512 did not allow the code to display the CatCoin stock price 
(while sometimes allowing the attack to still occur). Using Sha256 allowed for the CatCoin stock price to appear
when an attack was not happening. That being said, when an attack was happening I could not get the stock price
to appear while the XSS attack was being mitigated. I believe this is working as intended.

Using the source "https://jreddy1.w3.uvm.edu/getStock.js" for the Sha256 algorithm yielded the integrity value
of "sha256-75jche47CmmQ8L7hLjHEB/vztKWWOAjwx1iJOUpEebk=" and the crossorigin value of "anonymous".

-----------------------

__References__

Sri Hash Generator. SRI Hash Generator. (n.d.). https://www.srihash.org/ 