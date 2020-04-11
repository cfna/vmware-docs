# Updating Virtual Machine Configuration

In order to be able to run CrossFire on the Virtual Machine you just created, you will need to add some additional properties to you VMs configuration file.

If your Virtual Machine is still powered on, make sure to turn it off before editing the config file.

!!! tip
    If you want to copy CrossFire from your Host System make sure to do this before adjusting the configuration.  
    It seems like adjusting the configuration will break drag-and-drop feature.

## Adjust your configuration file

Find your Virtual Machines's Configuration file.  
The config file is located inside the directory you selected when setting up the Virtual Machine and is called `{YourVMName}.vmx`.  

Open the config file with any editor of your choice and append the following lines:

```
monitor_control.restrict_backdoor = "true"
isolation.tools.getPtrLocation.disable = "true"
isolation.tools.setPtrLocation.disable = "true"
isolation.tools.setVersion.disable = "true"
isolation.tools.getVersion.disable = "true"
monitor_control.disable_directexec = "true"
monitor_control.disable_btmemspace = "true"
```

Save the file and close it.  
You can now power it up again and proceed with the registry patch.  
