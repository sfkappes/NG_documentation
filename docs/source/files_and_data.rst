Files and Data 
=============================

**Data on Nightingale is LEGALLY PROTECTED.  Do NOT download ANY data without explicit permission.**

Users on Nightingale (you, if you're reading this) will have access to data that has, for instance, specific identifiable patient information that is protected by HIPAA Federal Law.  Users are directly responsible for protecting that data.  While the data resides on Nightingale, the system mechanisms help protect it.  However, downloading any part of that data, no matter how small, removes it from the protective measures of the system.  Downloading data from Nightingale may constitute a violation of Federal Law for which you could be prosecuted.  All downloads are  monitored and will be investigated.  If you have some need to pull data off of Nightingale that is not  protected, you should submit a ticket detailing what data you need to download, and why and how you intend to do that, and wait for an all-clear before you do the download.  

File Systems on Nightingale
---------------------------
Nightingale has a parallel files system, where both your user's home directory and your project's shared space live.  

Where *Your* Data Lives
---------------------
Nightingale is architected specifically to keep data protected both from people outside Nightingale and other Nightingale users.  Unlike other systems, we do not look at user data because we assume that any of your data could be HIPAA-covered information.  

Because of this compartmentalization, typically, you will already know where your data is located on Nightingale, because where that data lives will be part of the conversation between our staff and getting your team onto the system.  So if you're a Nightingale user and you don't know where your data lives, you should talk to your PI ("Principal Investigator") (that is, the person on your end, often your supervisor, who requested your user account).  If you are the project PI, or your PI doesn't know where the data is, then one of you should send in a ticket and ask, and we'll help you.  

If your data lives on a file system, it will likely be somewhere like /projects/sciteam/XXXX/ where "XXXX" will actually be a string of characters that correspond to your project.  You and the other users of your project will be able to see into that space and write data there, but other users, including staff, will not be able to see into it unless special measures are taken. 

Your data may also live on a database on a dedicated internal server.  If that's the case, you'll presumably know that, and have all the access information.  If not, or if the database isn't working for some reason, or you're having a problem, as always, submit a ticket.  
