You might be wondering how do I get my results of my analytical code 
out into the world so they can be used in publications or other studies. 

## What is allowed out?
Individual level data is not allowed out of the TRE. Any data out requests are reviewed by the Genes & Health core team to make sure they do not contain individual level data. Summary statistics, graphs etc are all usually fine.

## Existing data
XX

## Requesting data
You can make a request to download your results by right-clicking the file and selecting "request file download" for any file in /genesandhealth/red or /genesandhealth/pipeline folders. This sends an automated email to the Genes & Health team. If you have not received a response within 48h please feel free to chase us up (e.g. by Slack). The team will copy the data to either /green (for users of your sandbox only, to be able to download) or to /library-green (for all users to be able to download)(see above).

## Accessing TRE data from external systems/internet

Users can download data from green or library-green using linux command line gsutil (to install see [https://cloud.google.com/storage/docs/gsutil](https://cloud.google.com/storage/docs/gsutil)). Alternatively the browser based Google Cloud Console offers an easy method for simple storage tasks ([https://console.cloud.google.com/](https://console.cloud.google.com/)). Various other software tools also work with google storage.

Please note that whilst Finngen offers user upload using the green buckets, Genes & Health has decided not to implement this for data security reasons.

From your external system, ideally linux server rather than laptop if you are downloading lots of data (e.g. our GWAS).

Login to gcloud with _gcloud auth login_

Login with your [username@genesandhealth.qmul.ac.uk](mailto:username@genesandhealth.qmul.ac.uk) that you use for TRE access from your browser. It is likely to ask you to 2 Factor Authenticate either via phone or via a website link.

Run something like _gsutil ls gs://qmul-sandbox-production-library-green/_

Or better, from a multicore linux server, and especially if you are trying to transfer lots of data/files

_gsutil -m ls gs://qmul-sandbox-production-library-green/_

To transfer file use _gsutil -m cp_ or _gsutil -m rsync_

Lots of helpful information on gsutil via google search.