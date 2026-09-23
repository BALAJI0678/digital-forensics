#  Experinment - 02 

## Experiment Title

**Recover deleted or damaged files from a storage device using TestDisk**

## Aim

To analyse a storage device using TestDisk, identify the
required partition, verify its file structure, and perform
partition recovery operations.

## Tool Used

- TestDisk 7.2
- Windows
- 2 GB Virtual Test Disk
- NTFS File System

## Objective

The objective of this experiment is to understand how TestDisk
can be used to:

- Analyse a storage device
- Identify partitions
- Search for lost or damaged partitions
- Verify detected partitions
- List files from a partition
- Recover partition information
- Verify the file system structure

## Safety Precaution

The experiment was performed on a **2 GB virtual test disk**
instead of the actual laptop storage.

This was done to avoid accidental modification or data loss
on the actual system disk.

# Procedure

### Step 1: Launch TestDisk

The TestDisk application was extracted and `testdisk_win`
was executed as Administrator.

The **Create** option was selected to create a new log file.
<img width="1757" height="895" alt="Screenshot 2024-09-22 191516" src="https://github.com/user-attachments/assets/851ece61-136a-426f-86d0-88b4d5cabe28" />
### Step 2: Select the Storage Device

The available storage devices were displayed by TestDisk.

The **2 GB virtual test disk** was selected and
**Proceed** was chosen.
<img width="1808" height="870" alt="Screenshot 2024-09-22 081506" src="https://github.com/user-attachments/assets/2890d95f-fc62-4267-b8bb-af638ee62e30" />

### Step 3: Select Partition Table Type

The **Intel/PC (MBR)** partition table type was selected
for the virtual test disk.
<img width="1805" height="871" alt="Screenshot 2024-05-14 121356" src="https://github.com/user-attachments/assets/00930e6a-638b-4e44-a2b5-fa07088a1deb" />
### Step 4: Analyse the Disk

The **Analyse** option was selected to examine the current
partition structure and search for partitions.
<img width="1763" height="892" alt="Screenshot 2024-09-22 081556" src="https://github.com/user-attachments/assets/cc056fb3-1f57-45ad-83cc-c5fbd0171dae" />

### Step 5: Perform Quick Search

The **Quick Search** option was selected.

TestDisk scanned the virtual disk and identified the
NTFS partition.
<img width="1704" height="923" alt="Screenshot 2024-09-22 081507" src="https://github.com/user-attachments/assets/72732ef2-d543-4aff-be55-aefcd15fe047" />

### Step 6: Verify the Partition

The detected partition was displayed as:

`L HPFS - NTFS [TestDiskLab]`

The partition was selected for verification.
<img width="1706" height="922" alt="Screenshot 2024-09-22 098706" src="https://github.com/user-attachments/assets/690baa3e-3948-47bc-8c8a-01c46c66caa4" />


### Step 7: List Files

The **P** key was used to list the files present in the
detected partition.

TestDisk displayed the directory structure and available
files in the partition.
<img width="1676" height="939" alt="Screenshot 2024-05-14 121766" src="https://github.com/user-attachments/assets/cbe509d1-6d1d-4a6b-b495-311bf3709c87" />

### Step 8: Perform Deeper Search

The **Deeper Search** option was performed to conduct a
more thorough search of the storage device.

The detected partition was verified again.
<img width="1573" height="1000" alt="Screenshot 2024-05-14 123389" src="https://github.com/user-attachments/assets/1c27c453-490b-4407-8c69-7a8e234a4b5b" />


### Step 9: Write Partition Information

After verifying the correct partition, the **Write** option
was selected.

TestDisk displayed a confirmation message asking whether
the partition table should be written.

The operation was confirmed using **Y**.
<img width="1619" height="972" alt="Screenshot 2024-05-14 121316" src="https://github.com/user-attachments/assets/7a0e1de4-b5e8-4442-b6a0-3bc47b0fd8e3" />
### Step 10: Exit TestDisk

After the partition information was written successfully,
the TestDisk application was exited using the Quit option.

<img width="1649" height="954" alt="Screenshot 2024-05-14 192416" src="https://github.com/user-attachments/assets/5bd00216-d08e-4b20-9e24-678feae53c5a" />
# Final Output

The final TestDisk file-listing screen was used to verify
that the detected NTFS partition and its file structure
were accessible.
<img width="1653" height="952" alt="Screenshot 2024-05-14 191516" src="https://github.com/user-attachments/assets/b97cf452-2b41-4fec-888f-0d87d1dd3260" />

## Result

**TestDisk successfully analysed the virtual storage device,
identified the NTFS partition, verified its file structure,
and completed the partition recovery workflow.**



The experiment was safely performed using a virtual test disk
to avoid modifying the actual laptop storage.
