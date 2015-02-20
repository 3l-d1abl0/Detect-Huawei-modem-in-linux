<h1>
  Get your Huawei modem detected by your Linux Machine.
</h1>

<br>
For all this time i used the network manager to interact with my Huawei modem. But craving for a Gui for Mobile Partner(like the one in windows ) on Linux i decided to install the Mobile Partner setup for Linux on my Debian.	<br>
On trying the installation i ended up getting an <b> "Install NDIS driver failed "</b> error.	<br>

Searching over the net i found a way to tackle it. The folder with Mobile Partner installation files should have a compressed file "data.bin". on decompressing the file i found a whole new bunch of file s and folders. So in order to remove the NDIS error goto <b> "/data.bin/new/driver/ndis_driver/ndis_src/src/hw_cdc_driver.c" </b>	<br>

Goto the line <b> dbg ("cant't kmalloc dev"); </b> for me it was on line 1455, and comment it out <b> //dbg ("cant't kmalloc dev");</b>	<br>

I went through the whole process of installation an dyes this time <b>"The Linux NDIS driver is installed successfully"</b>.
But i still didn't get the Gui. it was not only the Gui, my datacard itself wasn't being detected. So i ended up uninstalling the setup but still couldn't get my modem detected.	<br>
By checking <i> lsusb </i> results i found out my modem was getting detected in a differnet mode.