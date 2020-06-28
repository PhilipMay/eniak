# Colab
- On GitHub: <https://github.com/googlecolab/colabtools>

## Download Files from Colab
```python
from google.colab import files
files.download('<file_to_download>') 
```

## Upload Files to Colab
```python
from google.colab import files
uploaded = files.upload()
```

## Mount Google Drive
```python
from google.colab import drive
drive.mount('/gdrive')
!ls -la /gdrive
```
