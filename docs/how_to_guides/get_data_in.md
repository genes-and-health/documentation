Sometimes it is necessary to get data or code into the TRE. As the
TRE is shut off from the internet this presents a challenge. This guide
explains how to do this.

## Copying text in
A small amount of text can be pasted in from external systems using the Clipboard tool. This does not allow copy/paste out. This might be useful should you need to copy in a difficult to write function for example. 

## Getting user data into the TRE
For the __Old TRE__, only admins can upload (larger amounts of) data into the TRE. Please put in a helpdesk request if you require new data or software upload. Please email [hgi@sanger.ac.uk](mailto:hgi@sanger.ac.uk) to set up a ticket.

For the __New TRE__, you can upload data to your Sandbox specific green-uploads bucket, which you can find using the widget below:

<div style="padding:0.5em;border:1px solid #000;border-radius:.1rem"><select style="display: block" onchange="this.nextElementSibling.setAttribute('href', this.nextElementSibling.innerText='https://console.cloud.google.com/storage/browser/qmul-production-sandbox-'+this.value+'_greenuploads')"><option value="1">Sandbox 1 - QMUL+WSI Core Team Desktop</option><option value="2">Sandbox 2 - External Academic Desktop</option><option value="3">Sandbox 3 - GSK Desktop</option><option value="4">Sandbox 4 - BMS Desktop</option><option value="5">Sandbox 5 - MSD Desktop</option><option value="6">Sandbox 6 - Takeda Desktop</option><option value="7">Sandbox 7 - Pfizer Desktop</option><option value="8">Sandbox 8 - S00050_FFAIR-PRS Desktop</option><option value="9">Sandbox 9 - Maze Therapeutics Desktop</option><option value="10">Sandbox 10 - Novo Nordisk Desktop</option><option value="11">Sandbox 11 - University of Exeter</option><option value="12">Sandbox 12 - Genomics PLC</option><option value="13">Sandbox 13 - AstraZeneca</option><option value="14">Sandbox 14 - External Academic, Consortium access</option><option value="15">Sandbox 15 - 5 Prime Sciences</option><option value="16">Sandbox 16 - Sandbox 16</option><option value="17">Sandbox 17 - Academic, NHS Digital access</option></select><a href="https://console.cloud.google.com/storage/browser/qmul-production-sandbox-1_greenuploads">https://console.cloud.google.com/storage/browser/qmul-production-sandbox-1_greenuploads</a></div>

Once uploaded, please email [hgi@sanger.ac.uk](mailto:hgi@sanger.ac.uk) with the names of the files/directories you'd like to be transferred and which Sandbox you like them to be transferred to.

> Please be aware at present, all users in your sandbox can see all data
that is being stored in the `green` bucket. For this reason, it is important that you do not upload any data that you do not want other users to see for example, individual level data.