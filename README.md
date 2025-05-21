# keyboardDisable
keyboard

✅ Use Group Policy Editor (Windows Pro only)
Win + R → type gpedit.msc

Go to:
Computer Configuration > Administrative Templates > System > Device Installation > Device Installation Restrictions

Enable:

Prevent installation of devices not described by other policy settings

Optionally, block specific device IDs

Let me know if you want steps to get your internal keyboard’s hardware ID so you can block it using Group Policy.



//CurrentOption
Option 2: Registry Edit to Disable i8042 Keyboard Driver
Since most laptop keyboards use the PS/2 interface managed by the i8042prt driver:

Open regedit

Navigate to:
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt

Change the Start DWORD value from 1 (automatic) to 4 (disabled)

Reboot

Note: This disables PS/2 keyboard and mouse drivers (built-in keyboard and touchpad). So make sure you have an external USB keyboard/mouse plugged in before doing this!






if you want to reenable it 
To open Registry Editor (regedit) in Windows:

✅ Step-by-Step:
Press Win + R to open the Run dialog.

Type:

nginx
Copy
Edit
regedit
Press Enter or click OK.

If prompted by User Account Control (UAC), click Yes.

Now you're inside the Windows Registry Editor.

Let me know if you want help navigating to the i8042prt key to disable the built-in keyboard driver.







You said:
once i do this and if i want enable later can i enable

Option 2: Registry Edit to Disable i8042 Keyboard Driver
Since most laptop keyboards use the PS/2 interface managed by the i8042prt driver:

Open regedit

Navigate to:
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt

Change the Start DWORD value from 1 (automatic) to 4 (disabled)

Reboot

Note: This disables PS/2 keyboard and mouse drivers (built-in keyboard and touchpad). So make sure you have an external USB keyboard/mouse plugged in before doing this!


ChatGPT said:
Yes, you can re-enable the built-in laptop keyboard later by reversing the registry change. Here's how:

🔧 To Disable the Built-in Keyboard (PS/2 interface):
Open regedit

Go to:

sql
Copy
Edit
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt
On the right pane, double-click Start

Change its value to:

Copy
Edit
4
➤ This disables the i8042prt driver (used for PS/2 keyboards and touchpads).

Reboot your laptop. The built-in keyboard and touchpad should stop working.

⚠️ Make sure an external USB keyboard/mouse is connected before doing this.

✅ To Re-Enable Later:
Just reverse the process:

Open regedit again

Go to the same key:

sql
Copy
Edit
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\i8042prt
Set Start value back to:

Copy
Edit
1
➤ This sets it to automatic startup again.

Reboot → Your built-in keyboard and touchpad should work again.

Let me know if you'd like me to give you a .reg file you can double-click to disable or enable this setting more easily.
