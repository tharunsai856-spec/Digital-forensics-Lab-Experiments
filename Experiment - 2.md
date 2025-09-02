# Experiment 2: Recover deleted or damaged files from a storage device using Test Disk

## Aim
The goal of this experiment is to demonstrate the process of recovering deleted or damaged files from a storage device using TestDisk, a free, open-source data recovery utility. The process focuses on retrieving files whose references in the file system have been lost or corrupted, allowing for the potential recovery of data that has been accidentally deleted.

## Description
TestDisk is a powerful, non-graphical command-line tool primarily designed to recover lost partitions and fix non-booting disks. As a secondary function, it can also recover deleted files from certain file systems, such as FAT, exFAT, NTFS, and ext2. Unlike its companion tool, PhotoRec, which recovers files based on their signatures (losing original filenames), TestDisk attempts to recover files while maintaining their original file names and directory structure. The procedure involves running the application, selecting the target storage device, analyzing its file system, and then navigating the detected directories to copy the deleted files to a new location.

## Tools & Equipment Used
A computer with a compatible operating system (Windows, Linux, or macOS).

TestDisk software: Downloaded and extracted from the official CGSecurity website. TestDisk is a portable application, so it doesn't require a formal installation.

Source Storage Device: The storage drive (e.g., hard drive, USB flash drive, or SSD) containing the deleted or damaged files.

Destination Storage Device: A separate, healthy storage medium with enough free space to save the recovered files. This is crucial to prevent overwriting the very data you're trying to recover.

## Procedure
Preparation: Download and extract the TestDisk ZIP file. Connect the source storage device to the computer. Do not save any new files to this device to avoid overwriting the deleted data.
![alt text](<Screenshot3/Screenshot 2025-09-02 162241.png>)

Launch TestDisk: Run the TestDisk executable with administrator privileges. On Windows, right-click the testdisk_win.exe file and select "Run as administrator."
![alt text](<Screenshot3/Screenshot 2025-09-02 162253.png>)

Create a Log File: When prompted, select "Create" to create a log file of the recovery session. This is a good practice for documentation.
![alt text](<Screenshot3/Screenshot 2025-09-02 162305.png>)

Select the Drive: Use the arrow keys to select the storage device you wish to scan from the list of detected drives. Press Enter to proceed. It's vital to choose the correct drive to avoid accidental damage to other partitions.
![alt text](<Screenshot3/Screenshot 2025-09-02 162316.png>)

Choose Partition Table Type: TestDisk will automatically detect the partition table type (e.g., Intel/PC). Select the default option or the correct type if you know it, and press Enter.

Select Undelete Files: From the main menu, select the "Advanced" option. In the next screen, highlight the specific partition where the files were deleted and choose the "Undelete" option at the bottom.
![alt text](<Screenshot3/Screenshot 2025-09-02 162328.png>)

Browse for Deleted Files: TestDisk will display a list of files and directories on the selected partition. Deleted files will typically be shown in red. Navigate through the directories using the arrow keys.

Recover and Copy: To recover a file or folder, highlight it and press the 'C' key. You will then be prompted to select a destination to save the recovered files. Navigate to your designated destination storage device and press 'C' again to confirm and copy the files.
![alt text](<Screenshot3/Screenshot 2025-09-02 162350.png>)

Complete the Process: Once the copying is complete, a confirmation message will appear. You can continue to recover other files or exit the program by pressing 'Q' to quit and then Enter.
![alt text](<Screenshot3/Screenshot 2025-09-02 162408.png>)

## Result
The experiment is successful if the deleted files are copied to the destination storage device and are accessible. A key indicator of success is that the recovered files retain their original filenames and folder structure. If the files are not found or are corrupted, it may be because their data blocks were overwritten after deletion. While TestDisk is an excellent tool for repairing file system structures and recovering recent deletions, its text-based interface and lack of a signature scanner can make it less effective for heavily corrupted drives or files that were deleted a long time ago. For those situations, the companion tool PhotoRec might be a better choice, though it doesn't preserve file names.