# Unzipping a File from Google Drive Using Google Colab

This repository contains a Google Colab script that demonstrates how to unzip a file stored on Google Drive. The script mounts your Google Drive in Colab, locates the zipped file, and extracts its contents to a specified directory within Google Drive.

## Task Overview

The goal of this task is to provide a convenient and efficient method for handling large datasets or multiple files bundled together in a single compressed file, directly from Google Colab. This process is particularly useful for data scientists, researchers, and developers who work with cloud storage.

## Steps Involved

1. **Mount Google Drive**: Access files stored in your Google Drive by mounting it in Google Colab.
2. **Locate the Zipped File**: Identify the path to the zipped file on your Google Drive.
3. **Unzip the File**: Use Python's `zipfile` module to extract the contents of the zipped file.
4. **Execute the Script**: Run the script in a Google Colab notebook cell.

## Usage Instructions

### 1. Mount Google Drive

First, mount your Google Drive to access your files:

```python
from google.colab import drive
drive.mount('/content/drive')
```

### 2. Define the Path and Extraction Directory

Update the paths to your zipped file and the extraction directory:

```python
zip_file_path = '/content/drive/MyDrive/path_to_your_zipped_file.zip'  # Update this path
extraction_path = '/content/drive/MyDrive/extracted_files/'  # Update this path
```

### 3. Unzip the File

Use the following code to unzip the file:

```python
import zipfile
import os

# Create the extraction directory if it does not exist
os.makedirs(extraction_path, exist_ok=True)

# Unzipping the file
with zipfile.ZipFile(zip_file_path, 'r') as zip_ref:
    zip_ref.extractall(extraction_path)

print('Unzipping complete. Files are extracted to:', extraction_path)
```

### 4. Run the Script

Execute the script in a Google Colab notebook cell. The script will unzip the file and store the extracted contents in the specified directory.

## Benefits

- **Convenience**: Easily manage and manipulate files stored in Google Drive directly from your browser.
- **Efficiency**: Handle large files without needing to download them to your local machine.
- **Accessibility**: Work from any device with internet access, leveraging the cloud storage capabilities of Google Drive.

## Contributing

Contributions are welcome! If you have any suggestions or improvements, feel free to open an issue or submit a pull request.



