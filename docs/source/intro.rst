Welcome to TTU's HPC... 
------------------------

This article is intended as a first-time user's guide to the Tennessee
Tech University High Performance Computer (HPC). If the materials
covered here do not answer your questions or you need additional
assistance, please complete the `HPC Issues
Ticket <https://services.tntech.edu/TDClient/1878/Portal/Requests/TicketRequests/NewForm?ID=s2jbAC%7eEZU8_&RequestorType=Service>`__.

.. container:: alert alert-danger

   If you have not yet requested access to the HPC and would like to do
   so, please complete the `HPC Access Request
   Form <https://services.tntech.edu/TDClient/1878/Portal/Requests/TicketRequests/NewForm?ID=EwwIhDonRRw_&RequestorType=Service>`__. 

Suggested Reading Order
-----------------------

-  `Introduction to Tennessee Tech University's High Performance
   Computer <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134358>`__ 
-  `HPC Interactive  <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134361>`__
-  `HPC: Batch
   Jobs <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134374>`__
-  `Spack Quick
   Reference <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134376>`__
-  `SLURM and HPCShell Quick
   Reference <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134379>`__
-  `Using
   Containers <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=112569>`__

Other Suggested Reading
-----------------------

-  `Open OnDemand for
   HPC <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134382>`__
-  `HPC - Open OnDemand Application -
   Jupyter Notebooks <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134542>`__
-  `Science
   DMZ <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134444>`__
-  `HPC Job
   Scheduling <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=112543>`__
-  `Submitting Groups of HPC Jobs with Job
   Arrays <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=112568>`__

Overview
--------

-  

   .. container::

      `Secure Shell (SSH) <#SSH>`__

-  

   .. container::

      `Login vs. Compute Nodes <#Nodes>`__

-  

   .. container::

      `Finding Your Application <#AppLocator>`__

   -  

      .. container::

         `Mac <#FindOnMac>`__

   -  

      .. container::

         `Linux <#FindOnLinux>`__

   -  

      .. container::

         `Windows <#FindOnWindows>`__

      -  

         .. container::

            `PuTTY for Windows <#Putty>`__

-  

   .. container::

      `Connecting to HPC  <#Connecting>`__

   -  

      .. container::

         `PuTTY <#ConnectingPutty>`__

   -  

      .. container::

         `Git Bash, PowerShell, Mac, Linux <#ConnectingOthers>`__

-  

   .. container::

      `Security Warning <#SecurityWarning>`__

-  

   .. container::

      `Logging In <#LoggingIn>`__

Secure Shell (SSH)
------------------

SSH  is a program that enables secure logins over an unsecured network.
It encrypts the data passing both ways so that it cannot be read if it
is intercepted.

SSH is client-server software, which means that both your local computer
(your laptop or desktop, for example) and the remote computer (in this
case, TTU's HPC) must have it installed. SSH server software is
installed on the HPC. You must ensure that SSH client software is
installed on your local machine. 

Free SSH clients for macOS, Windows, and Linux are available. For
Windows, one popular ssh client (GUI)
is \ `PuTTY <https://www.putty.org/>`__\ . PuTTY may be available via
the software center on TTU computers, and a command line version of ssh
is installed by default on Windows via PowerShell (for Windows 10 and up
since 2018) and on macOS or Linux via their Terminal applications. Git
Bash is another popular option for Windows but must be installed
separately. Git/Git Bash may be installed from \ \ `Git -
Downloads <https://git-scm.com/download>`__\ \ . 

.. _login-compute:

Login vs. Compute Nodes
-----------------------

TTU's HPC resources are divided between login nodes and compute nodes.
There are many compute nodes of different types, but only a small number
of login nodes.

Login nodes are used for administrative tasks like copying, editing, and
transferring files. When you connect to TTU's HPC via an ssh client, you
connect to one of the login nodes.

You cannot do your research computing on TTU's HPC login nodes. You can
connect to the compute nodes in an interactive session from the login
node or submit a batch job to the compute nodes.

Compute nodes are where your real work will be done. From a login node,
you can connect to one or more compute nodes in an interactive session
or submit a batch script to be run on one or more compute nodes.

You cannot log in to the compute nodes directly. Doing so would have a
detrimental effect on their performance and any jobs running on them.

Finding Your Application
------------------------

The initial processes for Mac, Linux, and Windows are slightly
different; however, once logged in, using the HPC should be the same for
all operating systems. Your username and password will be the same as
those you use for your TTU email, TechExpress, and other campus
services.

For Mac (do one of the following):
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

-  In the Finder |macOS Finder Image|

-  Click on Go, then find and click Utilities:

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=8e76fb0f-a986-44e1-b054-92c0714b308f.png&beidInt=386
   :alt: Utilities Location
   :class: img-responsive

-  Next, find and double-click Terminal:

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=6ffe8425-9144-44fb-89b4-8ee0429f4e02.png&beidInt=386
   :alt: Terminal Location
   :class: img-responsive

For Linux:
^^^^^^^^^^

Linux desktops can vary from system to system, but an application menu
should have a terminal (like a Mac system). If this is not the case,
consult your Linux distribution documentation. 

For Windows:
^^^^^^^^^^^^

Begin by locating and opening your chosen app (i.e., PuTTY, PowerShell,
Git Bash, etc.). Type the app's name in the search bar at the bottom
right of your screen.

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=b8383305-7fe5-49e9-8a28-1c1208f73b55.PNG&beidInt=386
   :alt: Windows Search Bar
   :class: img-responsive

If you have successfully downloaded and installed the application, you
should see an icon that will open it when double-clicked. 

`PuTTY for Windows <#ViaPuTTY>`__:
''''''''''''''''''''''''''''''''''

The PuTTY ssh client may be downloaded and installed
from \ `PuTTY.org <https://www.putty.org/>`__\ . This may already be
available if you use a campus device; check the software center. If you
prefer not to install, you can access TechAnywhere (\ `installation
instructions are available
here <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=111782>`__\ )
or open a PowerShell prompt and continue to the Git \ `Bash, PowerShell,
and Mac instructions <#Connecting>`__\ . For assistance in locating one
of these applications, see \ `FINDING YOUR
APPLICATION. <#AppLocator>`__\  

Connecting to the HPC
---------------------

PuTTY
~~~~~

From the PuTTY GUI, add the following in the location titled Host Name
(or IP address): username@login.hpc.tntech.edu

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=e972e2bb-48e2-4670-b355-83035c0c8027.PNG&beidInt=386
   :alt: PuTTY Configuration Window
   :class: img-responsive

You should not need to adjust the port number. 

Under 'Saved Sessions,' you may name this and push the save button.

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=445c7eaa-7f49-4cb8-adeb-ba25ba2d30b4.png&beidInt=386
   :alt: Saved Sessions Location
   :class: img-responsive

Once you have done this, you may click on 'Load' or 'Open.'

Proceed to `SECURITY WARNING <#SecurityWarning>`__

Git Bash, PowerShell, Mac, and Linux
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Note: For assistance with finding your chosen application see `FINDING
YOUR APPLICATION. <#AppLocator>`__ 

When prompted, type 'ssh username@login.hpc.tntech.edu'.

::

   PS C:\Users\sw-slcolson> ssh sw-slcolson@login.hpc.tntech.edu

Security Warning (Don't Be Alarmed)
-----------------------------------

The first time you connect to the HPC, you will see one of the attached
Security Alerts indicating that the server's host key is not cached.
This is a notification that your key has never made this connection
before, and you should click 'Accept' or type 'yes.' However, if you
ever see this message again when logging into the HPC, you should
immediately notify the \ `administrator (information listed at the top
of the article) <#Top>`__\ .

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=3c694101-6b57-4c5e-8e28-5bce2bc383a2.PNG&beidInt=386
   :alt: "The server's host key is not cached in the registry" security
   alert window
   :class: img-responsive

.. image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=173c30c1-4df6-4e6c-8600-d7abb6640e59.PNG&beidInt=386
   :alt: Insert Yes in PowerShell
   :class: img-responsive

Logging In
----------

Next, add your password. This will be your password for your TTU
email, TechExpress, and other campus services. Note that you will not
see any cursor movement as you type. 

Congratulations, you are on the Login Node!!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

|Login Node Window|

 
^

And now that we are all ready to begin...
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Please proceed to the next article in this series,  `HPC Interactive <https://services.tntech.edu/TDClient/1878/Portal/KB/ArticleDet?ID=134361>`__. 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

`Back to Top <#Top>`__
----------------------

.. |macOS Finder Image| image:: https://help.apple.com/assets/63D8162D4F5E9E311D0CFA28/63D816334F5E9E311D0CFA30/en_US/058e4af8e726290f491044219d2eee73.png
   :class: img-responsive
.. |Login Node Window| image:: https://services.tntech.edu/TDPortal/Images/Viewer?fileName=43e87b45-b997-439d-a717-ec06d95d5ef6.PNG&beidInt=386
   :class: img-responsive
