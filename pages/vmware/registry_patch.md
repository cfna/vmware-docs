# Patching the Windows Registry

If you try to start CrossFire on your Virtual Machine you will get an error similar to this:

```
Sorry, this application cannot run under a Virtual Machine
```

In order to get rid of this error, you'll have to patch some entries in your Virtual Machines's Registry.  

## Create/Download Registry Patch

There are two ways you can apply the registry patch. You can either download the already created registry patch file, or create it yourself.  
Below you can follow the instructions for your desired way to do so.

## Download the Registry Patch

!!! tip
    Here you can find a [video demonstration](https://www.youtube.com/watch?v=HsFENx_ewGo) of how to apply the registry patch & watch its results.  

Download the [registry-patch-cf.reg](https://github.com/PDDStudio/vmware-crossfire-patch/blob/master/patches/registry-patch-cf.reg) and save it to your Virtual Machine.
This registry patch contains some required values which need to be changed in order to bypass security checks.  

Once you have the file on your Virtual Machine, simply double-click to execute it.  
You will see an information and get asked if you want to continue, press `Yes` to apply the registry patch.  

![](../../img/registry-patch/registry-editor-warning.png)

!!! tip
    Usually you should be prompted by the Windows System to execute the registry patch as admin.  
    However, if not, try right click and select `Run as Administrator`.  

Once the changes applied successfully you're good to go.  

![](../../img/registry-patch/registry-editor-import-success.png)

## Create the Registry Patch manually

On your Virtual Machine, create a new text document and open it in Notepad.  
Paste the following content into the file:

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4D36E968-E325-11CE-BFC1-08002BE10318}\0000]
"DriverDesc"="Intel Graphics SVGA 3D"

[HKEY_LOCAL_MACHINE\HARDWARE\DESCRIPTION\System\BIOS]
"BaseBoardManufacturer"="Intel Corporation"
"SystemManufacturer"="Asus, Inc."
"SystemProductName"="Asus Platform"
```

Now select `File -> Save As` and name your file `registry-patch-cf.reg`.

!!! info
    When saving the file, make sure to select `Save as type:` to use `All Files`.  
    Otherwise you will not be able to execute the registry patch.

![](../../img/registry-patch/manual-save-as-sample.png)  

That's it. Now you can close your editor and search for the `registry-patch-cf.reg` file you just created and double-click to execute it.  
You will see an information and get asked if you want to continue, press `Yes` to apply the registry patch.  

![](../../img/registry-patch/registry-editor-warning.png)

!!! tip
    Usually you should be prompted by the Windows System to execute the registry patch as admin.  
    However, if not, try right click and select `Run as Administrator`.  

Once the changes applied successfully you're good to go.  

![](../../img/registry-patch/registry-editor-import-success.png)

