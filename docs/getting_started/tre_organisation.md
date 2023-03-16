When you log into your sandboxes, you will have a number of folders available for you. 
To get started we will concentrate on the `home`, `library-red` and `red` folders.

This [reference page](../explainers/file_structure.md) goes through the other folder and explain what they are for and how they should be used. 

## Your Home Folder
Available at `/home/ivm` in your sandbox, this is your personal folder. You can use this to store any files you want to keep, but it is not backed up. If you delete a file from here, it is gone forever.

If you have access to multiple sandboxes, your 
`/home` folder will be accessible from all of them.

### Home Folder Uses
You can use your home folder for any files you want to keep, but it is not backed up. The best place for this is in your `red/` folder.

`/home/ivm` is semi-fast (HDD) storage and as such is faster than other parts of the sandbox. It might be worth it to run some jobs here especially if you are loading large amounts of data but you should be aware that this is not backed up and therefore anything you want to keep should be moved to the `red/` folder.

## Types of data sensitivity
Folders are suffixed with `red` or `green` to indicate the type of data that is stored there. Red is for potentially sensitive data that should not be shared without the outside world. Green is for data that can be shared with the outside world.

## library-red 
Available at `/library-red` in your sandbox, this is a read-only folder that is shared between all users. This contains the data that you will want to use. 

`library-red` is slower storage of large capacity (\>8 PiB @ Feb 2022). For large files, the whole file needs to be read and cached first by gcsfuse, fileseek to a certain part of the file is not possible. For high performance/large files it may be better to make a copy to /red or /home/ivm.

`library-red` is a google storage bucket gs://qmul-sandbox-production-library-red/ (read+write only for admins)

## red
Used directly by the virtual machine.

Specific to each sandbox.

**Users should make a directory here to keep their data,** this can be read/write by all other users in the same sandbox.

/genesandhealth/red is semi-fast (HDD) storage of limited capacity (set at 1 TiB for most sandboxes, 10Tb for sandbox 1 @Feb 2022). Direct file seek to a certain part of the file is possible.

On Google Cloud Platform, the red drive is in Storage -\> Filestore.

/genesandhealth/red is a google bucket gs://fg-qmul-production-sandbox-1\_ivm/ (read only to admins, admins have to copy to it from within the TRE, not via external gsutil - gets deleted by the rsync) (replace the 1 with whichever sandbox you want)


