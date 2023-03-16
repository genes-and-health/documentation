Having selected your [_username@genesandhealth.qmul.ac.uk_](mailto:username@genesandhealth.qmul.ac.uk) account as your Chrome Profile (Google lets you colour Profiles in different colours/backgrounds which makes it easier to swop), point your Chrome browser to:

[https://qmul-production.genesandhealth.qmul.ac.uk/](https://qmul-production.genesandhealth.qmul.ac.uk/)

Or for a specific sandbox (if you know the number)

[https://qmul-production.genesandhealth.qmul.ac.uk/fg-qmul-production-sandbox-1/vm](https://qmul-production.genesandhealth.qmul.ac.uk/fg-qmul-production-sandbox-1/vm)

## Choosing your ivm ![](RackMultipart20230315-1-192w74_html_e4f2fe9a4377f88.png)

You will be offered a variety of virtual machine (ivm) types. Choose the **Standard** one. We suggest only using the other types ( **which cost more!** ) if there is a need for a particular script (e.g. high memory), and only once you have tested your script works on the Standard machine. Please actively turn these ivms off (see below) after your script has run.

Note that there are a few ivm types with lots of CPUs - these can be good for multithreaded applications such as plink or regenie that can make full use of these - sometimes these applications can run input/output too fast for the standard google bucket storage, and you might need to copy key files to local faster storage (see below).

## Switching off the ivm ![](RackMultipart20230315-1-192w74_html_dfe1e4ce26a23eb7.png)

Your virtual machine will keep running for 48 hours if you are doing nothing. You can disconnect from Chrome, turn your laptop off, and then you will be straight back into the exact same ivm when you connect again (within 48h). If you have linux jobs running, the ivm will keep going while these run (however long) plus another 48h.

Keeping ivms running in the background costs money. So **please actively shutdown (if you don't need the extra 48h) using the little off button on the bottom of the side menu.**
