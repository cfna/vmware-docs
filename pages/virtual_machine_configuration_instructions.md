# Virtual Machine Configuration Instructions & Registry Patch

> This page contains set up instructions to configure a Virtual Machine for being able to bypass security checks and play CrossFire West on it.

## Updating your Virtual Machine's Configuration

First make sure your Virtual Machine is powered off.  
Navigate into the folder where your VM files are located.  

The configuration file has the same name as your VM, with an `.vmx` extension.
Right click on the configuration file and select `Open with` -> `Notepad` (or any text editor of your choice).  

Append the content of the [`vmx.config`](../patches/vmx.config) file on the bottom of the configuration file, hit save and you're good to go.

You can now power on your machine again and proceed with the registry patch section below.

## Patching Registry Entries

It seems like the security check is evaluating certain registry Key-Value Pairs in order to determine if the Client is a normal PC or a VM.  
You can drag and drop the [registry-patch-cf.reg](../patches/registry-patch-cf.reg) into your VM's file explore and then simply double click & execute it.  
This will change the required registry Key-Value Pairs to an undetected value.  
Feel free to have a look at the content of the file and play with it yourself.  