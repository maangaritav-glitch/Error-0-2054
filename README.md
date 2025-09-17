# Error-0-2054
Error 0-2054 occurs when attempting to install or update Microsoft Office with the message:  "Cannot install this product in the selected update channel."
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Common\OfficeUpdate

Solution: Remove Conflicting Registry Key
The primary fix involves deleting a specific registry value that overrides the default update channel.

⚠️ Important Warning
Modifying the Windows Registry can cause serious system instability if done incorrectly. Proceed with caution and consider backing up your registry before making changes.

Step 1: Open Registry Editor
Press Win + R, type regedit, and press Enter.

Grant administrator permissions if prompted by UAC.

Step 2: Locate and Delete the Key
Navigate to the following key in the registry hierarchy:

text
HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Common\OfficeUpdate
In the right pane, look for a value named UpdateBranch or UpdateChannel.

Right-click on the value and select Delete.

Confirm the deletion.

Step 3: Perform a Clean Uninstall (Recommended)
A corrupted installation is often the root cause. Use Microsoft's official tool to ensure a complete removal.

Download and run the Microsoft Support and Recovery Assistant (SaRA) Office Uninstall tool:

https://aka.ms/SaRA-officeUninstall-fromPC

Execute the tool and follow its on-screen instructions to remove all Office products.

Restart your computer after the process completes.

Step 4: Reinstall Office
After restarting, install Office from your original source (e.g., Microsoft account portal, volume license service center, or installation media).

Additional Troubleshooting
If the error persists:

Check the same registry path under HKEY_CURRENT_USER and delete the UpdateBranch or UpdateChannel value if present.

HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Common\OfficeUpdate

For other installation issues, run the Microsoft Online Repair Tool:

https://aka.ms/SaRA-OfficeSCAR-FromPC

Root Cause
The error arises when a registry policy (often configured by a volume license installation) locks the Office update channel to a specific target (e.g., PerpetualVL2021). This conflicts with the update channel of the installer being used, preventing installation.
