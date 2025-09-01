## NAME: NAVEEN JAISANKER
## REG. NO.: 212224110039

# EXERCISE-3

Date: 01/09/2025

# AIM:

To develop a UiPath workflow that identifies PDF files from a given folder and moves them to a destination folder.

# PROCEDURE:

Step 1: Create a new UiPath Project

Open UiPath Studio and create a Sequence-based project.

Step 2: Define Variables

sourceFolder → String (e.g. "C:\Users\admin\Desktop\naveen\rpa")

destFolder → String (e.g. "C:\Users\admin\Desktop\pdfFolder")

pdfFiles → String[] (array of file paths)

currentItem → String (for iteration inside For Each)

Step 3: Assign Files

Use an Assign activity:

pdfFiles = Directory.GetFiles(sourceFolder)

Step 4: For Each Activity

Drag a For Each activity.

Set TypeArgument = String.

Loop through pdfFiles.

Store each item in currentItem.

Step 5: If Condition to check file type

Inside For Each, add an If Activity.

Condition:

Path.GetExtension(currentItem).ToLower().Equals(".pdf")


Then block:

Show a Message Box:
"PDF found: " & Path.GetFileName(currentItem)

Use Move File activity:

From: currentItem

To: Path.Combine(destFolder, Path.GetFileName(currentItem))

Enable Overwrite.

Else block:

(Optional) Show message: "Not a PDF file: " & currentItem.

# WORKFLOW:

Your workflow consists of:

A Sequence

An Assign activity to get all files from source folder

A For Each loop iterating through all files

An If activity to check for PDF extension

A Message Box to display found PDFs

A Move File activity to transfer PDFs to destination folder

# OUTPUT:

## BEFORE EXECUTION

Source Folder:

<img width="1919" height="1138" alt="Screenshot 2025-09-01 110400" src="https://github.com/user-attachments/assets/daa08330-e0ad-4082-9f46-5112ff7416fc" />


Destination Folder:

<img width="1919" height="1137" alt="Screenshot 2025-09-01 110410" src="https://github.com/user-attachments/assets/8356ddeb-86e7-4b11-abd4-1195fbb2bd79" />

## WORKFLOW EXECUTION

<img width="1919" height="1141" alt="Screenshot 2025-09-01 105756" src="https://github.com/user-attachments/assets/d4d24594-3cd5-4865-857a-fc6687250801" />

<img width="1919" height="1143" alt="Screenshot 2025-09-01 105844" src="https://github.com/user-attachments/assets/63c2c9e9-386b-49bd-b601-7378c5bd26c9" />

<img width="1919" height="1129" alt="Screenshot 2025-09-01 105851" src="https://github.com/user-attachments/assets/6ac71a63-e1f1-4595-9887-d9f2048e7790" />

<img width="1919" height="1134" alt="Screenshot 2025-09-01 105858" src="https://github.com/user-attachments/assets/c661fd04-e93d-4702-8987-bec8624896ca" />

<img width="1919" height="1139" alt="Screenshot 2025-09-01 110020" src="https://github.com/user-attachments/assets/d3b02001-c7da-4ef2-bf5b-3cd60cab8c8a" />

## AFTER EXECUTION

<img width="1919" height="1134" alt="Screenshot 2025-09-01 105919" src="https://github.com/user-attachments/assets/719ffd2c-2a56-4303-979f-27924d6d3811" />


# RESULT:

Thus, the UiPath workflow for identifying and moving PDF files from a source folder to a destination folder was designed and executed successfully.
