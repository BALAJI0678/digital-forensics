# Ex.No.7: Use AFLogical OSE to Extract Data from an Android Device

## Aim

To extract logical data such as contacts, SMS, and call logs from an Android device using AFLogical OSE and analyze the collected evidence for forensic purposes.


---

## STEP 1 — Prepare the Required Files

### Files Required

- Android Platform Tools (ADB)
- AFLogical OSE APK
- Google USB Driver for Windows
- Android device
- USB data cable

### Procedure

1. Create a main folder for the experiment:

   `C:\ForensicLab`

2. Create the following folders:

   `C:\ForensicLab\platform-tools\`

   `C:\ForensicLab\aflogical-ose\`

   `C:\ForensicLab\output\`

3. Place the downloaded files in their respective folders.

4. If the AFLogical OSE APK is not available, use the appropriate AFLogical OSE source or a forensic environment such as Santoku Linux.

---

## STEP 2 — Add Platform Tools to PATH

### Purpose

To allow ADB commands to be executed directly from Command Prompt.

### Procedure

1. Open:

   **Control Panel → System → Advanced system settings → Environment Variables**

2. Under **User Variables**, select **Path → Edit → New**.

3. Add the following platform-tools location:

   `C:\Users\venka\Downloads\platform-tools`

4. Click **OK** to save the changes.

### Verification

Open a new Command Prompt and execute:

```cmd
adb version
```
<img width="1492" height="1054" alt="Screenshot 2024-05-14 531316" src="https://github.com/user-attachments/assets/b96d668a-2d6d-42a2-9505-43267e928b2a" /><<img width="2149" height="732" alt="Screenshot 2024-05-14 129816" src="https://github.com/user-attachments/assets/6bd03076-9d13-454b-914b-3079d5aa4e18" />

## STEP 3 — Install Google USB Driver
Purpose
To enable the Windows computer to communicate with the Android device through ADB.
Procedure
1. Connect the Android phone to the computer using a USB data cable.
2. Open Device Manager.
3. Locate the connected Android device.
4. Right-click the device and select Update Driver.
5. Select Browse my computer for drivers.
6. Select the Google USB Driver folder.
7. Click Next and complete the installation.
Verification
Open Command Prompt and execute:
```cmd
adb devices
```
<img width="2132" height="737" alt="Screenshot 2024-05-14 121398" src="https://github.com/user-attachments/assets/6c20649f-b532-4cd7-80b3-36f789f531dd" />

## STEP 4 — Enable Developer Options on the Phone
Procedure
1. Open Settings on the Android phone.
2. Go to About phone.
3. Tap Build number seven times.
4. Return to Settings and open Developer options.
5. Enable:
   - USB debugging
   - Install via USB, if available.
  

## STEP 5 — Connect the Phone and Check ADB Connection
Purpose
To verify communication between the forensic workstation and the Android device.
Procedure
1. Connect the phone using a USB data cable.
2. Unlock the phone.
3. Open Command Prompt or PowerShell.
4. Execute:
```cmd
adb devices
```
5. If the phone displays an authorization request, select Allow USB debugging.
6. Run the command again:
```cmd
adb devices
```

## STEP 6 — Install AFLogical OSE on the Phone
Purpose
To install the forensic extraction application on the Android device.
Procedure
1. Ensure that the AFLogical OSE APK is available in:
   C:\ForensicLab\aflogical-ose\AFLogical-OSE.apk
2. Open Command Prompt.
3. Execute:
```cmd
adb install "C:\ForensicLab\aflogical-ose\AFLogical-OSE.apk"
```
4. Wait for the installation to complete.
5. The following message indicates successful installation:
<img width="2170" height="725" alt="Screenshot 2024-05-14 125366" src="https://github.com/user-attachments/assets/c02e9fa8-cbab-4ef7-b432-b247d80b4924" />
 
6. Check the Android device and verify that AFLogical OSE is installed.

## STEP 7 — Run AFLogical OSE and Extract Data
Purpose
To perform logical extraction of supported data from the Android device.
Procedure
1. Open the AFLogical OSE application on the Android device.
2. Grant the required permissions.
3. Select the available data categories for extraction, such as:
   - Contacts
   - SMS
   - Call Logs
   - MMS
   - MMS Parts
4. Start the extraction process.
5. Wait until the extraction is completed.
Verify the Extracted Data
The forensic output can be checked using:
```cmd
adb shell ls /sdcard/forensics
```


## STEP 8 — Copy Extracted Data to the Computer
Purpose
To transfer the extracted forensic data from the Android device to the computer for further examination.
Procedure
1. Create the output folder:
```cmd
mkdir C:\ForensicLab\output
```
<img width="2170" height="413" alt="Screenshot 2024-05-14 121355" src="https://github.com/user-attachments/assets/763b2c45-c7e5-4a9c-b655-dd96113c2e30" />adb pull /sdcard/forensics/ "C:\ForensicLab\output"
```
3. Wait for the transfer to complete.
4. Check the transferred files using:
```cmd
dir "C:\ForensicLab\output"
```


<img width="1837" height="856" alt="image" src="https://github.com/user-attachments/assets/fd8f754a-ecaf-48e0-8fce-34fe836fcec4" />


## STEP 9 — Verify Integrity Using SHA-256
Purpose
To verify the integrity of the extracted forensic evidence.
Windows PowerShell
Execute:

Get-FileHash "C:\ForensicLab\output\<extracted-file>" -Algorithm SHA256

Record the generated SHA-256 hash value in the forensic report.
Linux/macOS
sha256sum <extracted-file>


## STEP 10 — Clean Up
After completing the extraction:
1. Close the AFLogical OSE application.
2. Uninstall AFLogical OSE from the Android device if required.
3. Disconnect the Android device safely.
4. Preserve the extracted forensic files and recorded hash values for documentation.


# Result
The Android device was successfully connected to the forensic workstation using ADB. AFLogical OSE was installed and used to perform logical extraction of the supported mobile data. The extracted forensic output was transferred to the computer and examined for available contacts, SMS, call logs, MMS, and related information. SHA-256 hashing was used to verify the integrity of the selected extracted evidence.
