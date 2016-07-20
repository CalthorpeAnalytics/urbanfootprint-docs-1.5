# UrbanFootprint ArcMap Integration Tool

## System Requirements / Supported Version
 - ArcMap 10.3
 - ArcMap 10.4

## Download
[Arc Toolbox Version 1.0.0](https://s3-us-west-2.amazonaws.com/uf-provisioning/urbanfootprint-arc-toolbox-v1.0.0.zip)

## Steps to Download UrbanFootprint Upload Toolbox
1. Open ArcMap
2. Navigate to the ArcToolbox section
3. Right click on ArcToolbox and select 'AddToolbox...'

    ![arc_toolbox_1](images/arc_add_toolbox.png)

4. Navigate to the Upload toolbox and click open

    ![arc_toolbox_2](images/arc_add_toolbox_2.png)

5. You should now see it at the bottom of your ArcToolbox

    ![arc_toolbox_3](images/arc_add_toolbox_3.png)

    ![arc_toolbox_4](images/arc_add_toolbox_4.png)


***Tip:*** If you would like the toolbox to appear every time you launch ArcMap,
right click on the ArcToolbox again and select Save Settings > To Default

![arc_toolbox_5](images/arc_add_toolbox_5.png)

## How to use the UrbanFootprint Upload Toolbox
This customized python toolbox (.pyt) allows ArcMap users to upload their layers
directly to UrbanFootprint with built-in ArcMap functionality.

### UrbanFootprint Upload Toolbox
![arc_tool](images/arc_tool_1.png)

This ArcMap toolbox has 5 inputs described below:

**Email:** The email address used to login to UrbanFootprint

**Password:** The password used to login to UrbanFootprint

**Server URL:** The url of UrbanFootprint (Example: https://example.urbanfootprint.net)

**Project Name:** The name of the project in UrbanFootprint - *case sensitive* (Example: Anaheim)

**Input Features:** Drag a layer from ArcMap or browse to the layer using the ![browse_files](images/arc_tool_browse_files.png)

### Upload Toolbox Instructions
1. Enter all of the above fields and click OK
2. After the dialog succeeds, open UrbanFootprint
3. Your layer is now in UrbanFootprint!

## Troubleshooting
If your layer is not in UrbanFootprint, please try the following steps:

1. Navigate to the 'Results' section in ArcMap and view the messages.

    ![arc_troubleshoot_1](images/arc_tool_troubleshoot_1.png)
    ![arc_troubleshoot_2](images/arc_tool_troubleshoot_2.png)

2. Look for an 'ExecuteError' in the messages.
In this example, the Server URL is incorrect.
![arc_troubleshoot_3](images/arc_tool_troubleshoot_3.png)

3. Address the issue listed in the messages and try upload again.

***Hint:*** To see the error right away, try showing the 'Details'
of your toolbox. This dialog pops up after you click OK on the
Upload tool.
![arc_troubleshoot_4](images/arc_tool_troubleshoot_4.png)


