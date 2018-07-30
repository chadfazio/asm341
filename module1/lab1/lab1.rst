Lab 1.1: Allowed URL List
----------------------------------------

.. |lab-1| image:: images/lab-1.png
.. |lab1-1| image:: images/lab1-1.png
.. |lab1-2| image:: images/lab1-2.png
.. |lab1-3| image:: images/lab1-3.png
.. |lab1-4| image:: images/lab1-4.png
.. |lab1-5| image:: images/lab1-5.png
.. |lab1-6| image:: images/lab1-6.png
.. |lab1-7| image:: images/lab1-7.png
.. |lab1-8| image:: images/lab1-8.png



Task 1 - Create a Security Policy and Enable Logging
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#.  Browse to the BIGIP management console by opening FireFox and clicking on the **bigip01** shortcut.
#.  Login with the credentials username: **f5student** and the password: **f5DEMOs4u!**
#.  Navigate to **Local Traffic -> Virtual Servers -> Virtual Server List** and then click on **asm_vs**
#.  Change HTTP profile from **None** to **HTTP**
        |lab-1|
#.  Create a new ASM policy by navigating to **Security -> Application Security -> Security policies**.
#.  Click **Create New Policy** and fill in the page as follows, then click **create policy**
	|lab1-1|
#.  Navigate to **Local Traffic -> Virtual Servers -> asm_vs -> Security -> Policies**.
#.  Enable logging profiles then add the "Log All Requests" profile as shown below, and click **update**
	|lab1-2|
#.  Finally, lets configure this ASM policy to Alarm and Block "Illegal URLs".
	|lab1-6|


Task 2 - Examine the Allowed URLs list
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#.  Open a new firefox tab and login to ``http://10.1.10.145/WebGoat`` (credentials are f5student / f5DEMOs4u!)
#.  Explore around the app.  Notice as you click between (for instance) **Injection Flaws**  and **Authentication Flaws**  that the URL changes to correspond to the page.  We can use this information to build policy in our WAF.
#.  Return to the BIG-IP UI and navigate to **Security -> Application Security -> URLs -> Allowed URLs**
	|lab1-3|
#.  Our WAF is currently set to allow **any** URL as represented by the wildcard entries.  
#.  We can verify the WAF is seeing the traffic by navigating to **Security -> Event Logs -> Application -> Requests** and inspecting the entries.
	|lab1-4|
#.  Don't forget to clear the "Illegal Requests" filter!
	|lab1-5|


Task 3 - Modify the Allowed URLs list 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#.  Return to the Allowed URLs list.
#.  Delete the HTTP and HTTPS Wildcard entries.
	|lab1-7|
#.  Click the **Apply Policy** button
#.  Attempt to browse the test site ``http://10.1.10.145/WebGoat`` , what are your results?
#.  Now lets add an Allowed URL.  Click the **Create** button and create an allowed URL with the following settings:
	|lab1-8|
#.  Click **Apply Policy** button.
#.  Test site again and compare results.  

Task 4 - Create Explicit Allowed URLs
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#.  Now that we've seen how wildcard URLs work, let's get the site to work with explict URLs.  
#.  Delete the Wildcard URL /WebGoat/
#.  Click **Apply Policy**
#.  Create explict URLs to allow access to **only** the login page, landing page, and Insecure Login Page.
