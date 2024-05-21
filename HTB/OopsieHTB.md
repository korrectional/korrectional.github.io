Today (May 14) I'll be giving a walkthrough on the Oopsie box in HTB.
Note that I will be skipping generic steps and will only focus on the technicality of the exploits, so this is not necessarely a guide to solve this
box, but more of a technical review of what we did to solve it.


1 - First, our nmap indicated that the port 81 hosts an Apache web server, so we opent he IP and we end up in a website about EVs.
2 - Using a web crawler, we find that there are a couple of hidden pages, including a login page.
      Web crawler- a type of bot that's often used by search engines to map out websites. Basically it just goes through the html for links to other 
      pages, and because it's often used by search engines it doesn't raise suspicions. We used Blurp to do this.
3 - After we logged in as guests, there was a page describing the id of our guest id, and after channg the page from ?user=2 to ?user=0 (something
      that probabilty only existed many years ago in the early internet) and  we got the id of an admin user
4- Then we open the storage in the inspect panel and change the user id and name in the cookies to admin and admin id.
5- Because the admin has the possibility to upload files, we upload a php inverse shell and that's it!

Now you have access to the machine (but you also need to elevate your privileges...)
