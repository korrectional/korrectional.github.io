This text used to be together with the intro, but since my knwlodge is always growing, I decided to keep this as it's own thing.

Stuff I learned:

Sadly for me, the Tiers 0 and 1 of HTB teach us to rely on systems that are heavily misconfigured, or have no passwords at all, what makes me feel
stupid because I soon as we got to slightly more complicated stuff I felt very lost. Aside from "use admin/root" for login, here's what I remember I
learned (it's absolutely not in order, skip this if you wish)
1- Some websites have hidden directories that are not proprely protected
2- On login pages, because of how SQL is built, using an # might disrupt the code and there would be no need for a password (SQL Injection)


3- Something very interesting is that active languages like php and python can consider user input as commands if the website is not coded proprely,
    so the use of commands is possible. In Server-Side Template Injection, if the input is added to the template and not to the data, we can try
    to use commands that will elevate our permissions to the point of root (some python libraries import OS even though you can't do it directly
    in the website)
4- Many different ports have different processes, and some are more exploitable with others. Exploiting one port might eventuallylead to exploitation
    of others
5- NTLM login can be exploited by intercepting a hash and trying to create a hash that is the same (effectively bruteforcing)
