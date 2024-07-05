Having selected your [_username@genesandhealth.qmul.ac.uk_](mailto:username@genesandhealth.qmul.ac.uk) account as your Chrome Profile, point your Chrome browser to one of the following URLs:

- __New TRE__ - [https://new-production.genesandhealth.qmul.ac.uk/](https://new-production.genesandhealth.qmul.ac.uk/) - If you've been notified that your sandbox has been transitioned to the new version.
- __Old TRE__ [https://qmul-production.genesandhealth.qmul.ac.uk/](https://qmul-production.genesandhealth.qmul.ac.uk/)

This will take you to the TRE login page. You will be asked to enter your username and password. The username is the one you have been given by the Genes and Health team, and the password is the one you have set up when you first logged in.

If you want to go a specific sandbox, you can use the following URL, and replace the sandbox number with the one you want to access:

<div style="padding:0.5em;border:1px solid #000;border-radius:.1rem"><select style="display: block" onchange="this.nextSibling.nextElementSibling.setAttribute('href', this.nextElementSibling.nextSibling.innerText='https://qmul-production.genesandhealth.qmul.ac.uk/fg-qmul-production-sandbox-'+this.value+'/vm');this.nextElementSibling.setAttribute('href', this.nextElementSibling.innerText='https://new-production.genesandhealth.qmul.ac.uk/qmul-production-sandbox-'+this.value+'/vm')"><option value="1">Sandbox 1 - QMUL+WSI Core Team Desktop</option><option value="2">Sandbox 2 - External Academic Desktop</option><option value="3">Sandbox 3 - GSK Desktop</option><option value="4">Sandbox 4 - BMS Desktop</option><option value="5">Sandbox 5 - MSD Desktop</option><option value="6">Sandbox 6 - Takeda Desktop</option><option value="7">Sandbox 7 - Pfizer Desktop</option><option value="8">Sandbox 8 - S00050_FFAIR-PRS Desktop</option><option value="9">Sandbox 9 - Maze Therapeutics Desktop</option><option value="10">Sandbox 10 - Novo Nordisk Desktop</option><option value="11">Sandbox 11 - University of Exeter</option><option value="12">Sandbox 12 - Genomics PLC</option><option value="13">Sandbox 13 - AstraZeneca</option><option value="14">Sandbox 14 - External Academic, Consortium access</option><option value="15">Sandbox 15 - 5 Prime Sciences</option><option value="16">Sandbox 16 - Sandbox 16</option><option value="17">Sandbox 17 - Academic, NHS Digital access</option></select><a style="display: block" href="https://qmul-production.genesandhealth.qmul.ac.uk/fg-qmul-production-sandbox-1/vm">https://new-production.genesandhealth.qmul.ac.uk/qmul-production-sandbox-1/vm</a><a href="https://qmul-production.genesandhealth.qmul.ac.uk/fg-qmul-production-sandbox-1/vm">https://qmul-production.genesandhealth.qmul.ac.uk/fg-qmul-production-sandbox-1/vm</a> - For the old version.</div>

## Choosing your ivm !

Once you have logged in, you will be taken to the **Virtual Machines** page. Here you can start a new ivm, or connect to an existing one.

![IVM](images/ivm.png)

You will be offered a variety of virtual machine (ivm) types. Choose the **Standard** one. We suggest only using the other types ( **which cost more!** ) if there is a need for executing particular script that uses high memory or requires increased CPU capacity, and only once you have tested your script works on the Standard machine. 

Note that there are a few ivm types with lots of CPUs - these can be good for multithreaded applications such as plink or regenie that can make full use of these - sometimes these applications can run input/output too fast for the standard google bucket storage, and you might need to copy key files to local faster storage (see below).

## Switching off the ivm ![](RackMultipart20230315-1-192w74_html_dfe1e4ce26a23eb7.png)

Your virtual machine will keep running for 48 hours if you are doing nothing. You can disconnect from Chrome, turn your laptop off, and then you will be straight back into the exact same ivm when you connect again (within 48h). If you have linux jobs running, the ivm will keep going while these run (however long) plus another 48h.

Keeping ivms running in the background costs money. So **please actively shutdown (if you don't need the extra 48h) using the little off button on the bottom of the side menu.**
