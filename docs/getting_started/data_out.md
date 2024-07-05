You might be wondering how do I get my results of my analytical code 
out into the world so they can be used in publications or other studies. 

## What is allowed out?
Individual level data is not allowed out of the TRE. Any data out requests are reviewed by the Genes & Health core team to make sure they do not contain individual level data. Summary statistics, graphs etc are all usually fine.

## Existing data
There are number of files in `library-green` that are available for download. These do not need a request to be made.

## Requesting data
You can make a request to download your results by right-clicking the file and selecting "request file download" for any file in /genesandhealth/red or /genesandhealth/pipeline folders. This sends an automated email to the Genes & Health team. If you have not received a response within 48h please feel free to chase us up (e.g. by Slack). The team will copy the data to either /green (for users of your sandbox only, to be able to download) or to /library-green (for all users to be able to download)(see above).

## Accessing TRE data from external systems/internet

For the __Old TRE__, users can download data from green or library-green using linux command line gsutil (to install see [https://cloud.google.com/storage/docs/gsutil](https://cloud.google.com/storage/docs/gsutil)). Alternatively the browser based Google Cloud Console offers an easy method for simple storage tasks ([https://console.cloud.google.com/](https://console.cloud.google.com/)). Various other software tools also work with google storage.

For the __New TRE__, users can download data from greendownloads or library-green using linux command line [gsutil](https://cloud.google.com/storage/docs/gsutil).

Alternatively, you can use the web-interface for your Sandbox specific green-downloads bucket, which you can find using the widget below:

<div style="padding:0.5em;border:1px solid #000;border-radius:.1rem"><select style="display: block" onchange="this.nextElementSibling.setAttribute('href', this.nextElementSibling.innerText='https://console.cloud.google.com/storage/browser/qmul-production-sandbox-'+this.value+'_greendownloads')"><option value="1">Sandbox 1 - QMUL+WSI Core Team Desktop</option><option value="2">Sandbox 2 - External Academic Desktop</option><option value="3">Sandbox 3 - GSK Desktop</option><option value="4">Sandbox 4 - BMS Desktop</option><option value="5">Sandbox 5 - MSD Desktop</option><option value="6">Sandbox 6 - Takeda Desktop</option><option value="7">Sandbox 7 - Pfizer Desktop</option><option value="8">Sandbox 8 - S00050_FFAIR-PRS Desktop</option><option value="9">Sandbox 9 - Maze Therapeutics Desktop</option><option value="10">Sandbox 10 - Novo Nordisk Desktop</option><option value="11">Sandbox 11 - University of Exeter</option><option value="12">Sandbox 12 - Genomics PLC</option><option value="13">Sandbox 13 - AstraZeneca</option><option value="14">Sandbox 14 - External Academic, Consortium access</option><option value="15">Sandbox 15 - 5 Prime Sciences</option><option value="16">Sandbox 16 - Sandbox 16</option><option value="17">Sandbox 17 - Academic, NHS Digital access</option></select><a href="https://console.cloud.google.com/storage/browser/qmul-production-sandbox-1_greendownloads">https://console.cloud.google.com/storage/browser/qmul-production-sandbox-1_greendownloads</a></div>

From your external system, ideally linux server rather than laptop if you are downloading lots of data (e.g. our GWAS).

Login to gcloud with _gcloud auth login_

Login with your [username@genesandhealth.qmul.ac.uk](mailto:username@genesandhealth.qmul.ac.uk) that you use for TRE access from your browser. It is likely to ask you to 2 Factor Authenticate either via phone or via a website link.

Run something like _gsutil ls gs://qmul-sandbox-production-library-green/_

Or better, from a multicore linux server, and especially if you are trying to transfer lots of data/files

_gsutil -m ls gs://qmul-sandbox-production-library-green/_

To transfer file use _gsutil -m cp_ or _gsutil -m rsync_

Lots of helpful information on gsutil via google search.