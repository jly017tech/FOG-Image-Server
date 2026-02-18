
<h1>Ubuntu FOG Server </h1>

<img width="1159" height="728" alt="IT-Homelab_ FOG Server (2)" src="https://github.com/user-attachments/assets/adfda0b7-7ac0-46b1-839f-1fd6459ddd7d" />


<p>
  FOG stands for Free Opensource ghost program allows anyone to capture image and deploy multiple segment at a same time.
  In this lab, I'm demonstrating how to capture the Windows 11 Client that I customize that has already install apps. I will configure FOG server network IP address to match with
Windows Server DC - HuskyTech.local and using HuskyTech.local server to capture the image and upload to the FOG server I setup.</p>



<h2>Adding Ubuntu FOG Server to the HuskyTech.Local</h2>
<img width="1603" height="862" alt="image" src="https://github.com/user-attachments/assets/0f87d9c7-464c-4493-bc1d-94156a2ab95e" />


<h2>FOG Installation Setup: </h2>
<p>I download from the official github where FOG developers update their main branch where is the most recommend to download the folder.
After downloading the folder, I went ahead execute the installfog.sh and follow each questions carefully</p>

<p> Version: 1.5.10.1763 Installer/Updater

  What version of Linux would you like to run the installation for?

          1) Redhat Based Linux (Redhat, Alma, Rocky, CentOS, Mageia)
          2) Debian Based Linux (Debian, Ubuntu, Kubuntu, Edubuntu)
          3) Arch Linux

  Choice: [2] 



  Starting Debian based Installation


  FOG Server installation modes:
      * Normal Server: (Choice N) 
          This is the typical installation type and
          will install all FOG components for you on this
          machine.  Pick this option if you are unsure what to pick.

      * Storage Node: (Choice S)
          This install mode will only install the software required
          to make this server act as a node in a storage group

  More information:  
     http://www.fogproject.org/wiki/index.php?title=InstallationModes

  What type of installation would you like to do? [N/s (Normal/Storage)] N

  We found the following interfaces on your system:
      * enp0s3 - 10.0.2.20/24

  Would you like to change the default network interface from enp0s3?
  If you are not sure, select No. [y/N] N

  Would you like to setup a router address for the DHCP server? [Y/n] Y
  What is the IP address to be used for the router on
      the DHCP server? [10.0.2.1]

  Would you like DHCP to handle DNS? [Y/n] N

  Would you like to use the FOG server for DHCP service? [y/N] N

  This version of FOG has internationalization support, would  
  you like to install the additional language packs? [y/N] N

  Using encrypted connections is state of the art on the web and we
  encourage you to enable this for your FOG server. But using HTTPS
  has some implications within FOG, PXE and fog-client and you want
  to read https://wiki.fogproject.org/HTTPS before you decide!
  Would you like to enable secure HTTPS on your FOG server? [y/N] N

  Which hostname would you like to use? Currently is: FOGSERVER
  Note: This hostname will be in the certificate we generate for your
  FOG webserver. The hostname will only be used for this but won't be
  set as a local hostname on your server!
  Would you like to change it? If you are not sure, select No. [y/N] N
  FOG would like to collect some data:
      We would like to collect the following information:
        1. OS Name (CentOS, RedHat, Debian, etc....)
        2. OS Version (8.0.2004, 7.2.1409, 9, etc....)
        3. FOG Version (1.5.9, 1.6, etc....)

  What is this information used for?
      We would like to simply track the common types of OS
      being used, along with the OS Version, and the various
      versions of FOG being used.

  Are you ok with sending this information? [Y/n] N
</p>






<h2>FOG Server Configuration Changes</h2>
<ul>
  <li>General settings -> FOG_WOL_Host</li>
  <li>TFTP Server -> Change FOG_TFTP_HOST and FOG_PXE_IMAGE_DNSAddress </li>
  <li>Web Server -> FOG_Web_Host </li>
  <li>Stirage Management -> Default Member -> IP Address</li>
  <li>cd /opt/fog/.fogsettings </li>
</ul>
