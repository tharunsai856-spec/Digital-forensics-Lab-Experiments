# Experiment 1: Create a forensic image of a storage device's using FTK Imager

## Aim
The aim of this experiment is to create a forensically sound, bit-for-bit image of a storage device using FTK Imager. This process ensures the integrity of the original evidence is maintained, preventing any alteration or damage. The resulting forensic image can be used for analysis without affecting the source media, and its integrity is verified through a hash value.

## Description
Forensic imaging is the process of creating a perfect, bit-stream copy of a storage device, such as a hard drive or USB flash drive. Unlike a simple file copy, a forensic image duplicates every sector of the source device, including all active data, deleted files, and unallocated space. FTK Imager, a free tool from AccessData (now Exterro), is a popular choice for this task. The process involves connecting the evidence drive in a read-only manner, creating the image file, and then verifying its hash value to confirm it is an exact replica of the original.

## Tools & Equipment Used
Acquisition/Forensic Workstation: A dedicated computer used for digital forensics. It should be clean and not contain any data from the case.

FTK Imager: The primary software tool used for creating the forensic image.

Write-Blocker: A crucial hardware or software device that prevents any data from being written to the source storage device. This ensures the integrity of the original evidence is preserved.

Source Storage Device: The original evidence to be imaged (e.g., a hard drive, USB drive, or SSD).

Destination Storage Device: A separate, sanitized hard drive or storage medium with enough space to store the forensic image.

Cables and Adapters: Necessary cables (e.g., SATA, USB) to connect the source device to the write-blocker and then to the acquisition workstation.

## Procedure
Preparation and Connection: Ensure the forensic workstation is ready. Connect the source storage device to the forensic workstation using a hardware write-blocker. This step is critical to prevent any changes to the original data.
![alt text](<Screenshots/Screenshot 2025-09-02 141329.png>)

Launch FTK Imager: Open the FTK Imager application on the forensic workstation.
![alt text](<Screenshots/Screenshot 2025-09-02 141349.png>)

Start the Imaging Process: From the menu, go to File > Create Disk Image.
![alt text](<Screenshots/Screenshot 2025-09-02 141401.png>)

Select the Source: In the "Select Source" dialog, choose the Physical Drive option. Then, from the dropdown list, select the physical drive that corresponds to your connected evidence device.
![alt text](<Screenshots/Screenshot 2025-09-02 141423.png>)

Choose Image Destination and Format: Click Add to specify the destination for the forensic image. You will be prompted to select an image type. Common formats include:

Raw (dd): A bit-by-bit copy without any additional metadata.
![alt text](<Screenshots/Screenshot 2025-09-02 141457.png>)

E01 (EnCase Forensic Image): A popular format that includes case information, a hash of the image, and optional compression.

AFF (Advanced Forensic Format): An open-source format designed for digital forensics.
![alt text](<Screenshots/Screenshot 2025-09-02 141440.png>)

Add Evidence Information: Fill out the case information, such as the case number, evidence number, unique description, and examiner's name. This information is embedded in the forensic image file and is important for maintaining the chain of custody.
![alt text](<Screenshots/Screenshot 2025-09-02 141604.png>)

Initiate Imaging and Verification: Specify the destination path on your destination storage device, give the image a filename, and check the option to verify images after they are created. This will automatically calculate and compare hash values after the image is created, ensuring the copy is identical to the original.

Monitor and Finalize: Click Start to begin the imaging process. FTK Imager will display a progress bar. Once the imaging is complete, the verification process will automatically start. Upon completion, a summary report will be generated showing the hash values of the source and the created image.
![alt text](<Screenshots/Screenshot 2025-09-02 141648.png>)

## Result
Upon completion of the imaging process, a forensic image file (e.g., .E01 or .dd) and a corresponding text report will be created. The report will display the hash values (e.g., MD5 and SHA1) of the source drive and the newly created image. The experiment is successful if these hash values match. A matching hash confirms that the forensic image is a true and unaltered copy of the original evidence, allowing a digital forensics investigator to proceed with analysis on the image without risking the integrity of the original evidence.

The FTK Imager process is demonstrated in this video, which shows how to create a forensic image of a physical drive.