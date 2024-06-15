# Unzipping a File from Google Drive Using Google Colab

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




