# DataOCREnhance README

This Python script provides functionality for Optical Character Recognition (OCR) using Tesseract and OpenCV libraries. It includes features for preprocessing images, extracting text from images, drawing bounding boxes, and comparing OCR results with ground truth annotations.

## Overview

The OCR functionality consists of several classes and methods:

- `OCR_Config`: Data class for storing configuration parameters.
- `Ocr_Function`: Class containing OCR-related methods.
- `json_conf_load`: Class for loading JSON configuration files.

## Usage

### OCR_Config

This class handles configuration parameters for OCR functionality. Parameters include paths to image files, JSON files, and annotation files, as well as various settings for preprocessing, output visualization, and logging.

### Ocr_Function

This class contains methods for performing OCR tasks:

- `ocr_v2`: Perform OCR on an image using Tesseract with specified parameters.
- `preprocess_image`: Preprocess an image for better OCR results, including resizing, contrast enhancement, and binarization.
- `draw_boundbox`: Draw bounding boxes around detected objects in an image.
- `OCR_All_Field`: Perform OCR on all fields in an image, compare results with ground truth, and save output as JSON files.
- `ocr_entirefile`: Perform OCR on all images in a directory.

### json_conf_load

This class loads JSON configuration files for OCR functionality.

## Example Usage

```python
# Set Tesseract path
OCR_Config.set_tesseract_path(r'D:\Program Files\Tesseract-OCR\tesseract.exe')

# Load JSON configuration
json_loader = json_conf_load(r"ocr_config.json")
ocr_functionality = json_loader.get_ocr_function_instance()

# Define custom preprocessing function
def custom_imageppf(image_array):
    edge = cv2.Canny(image=image_array, threshold1=100, threshold2=200)
    return edge

# Perform OCR on entire directory with custom preprocessing
ocr_functionality.ocr_entirefile(r"Test/image", cust_preprocess_func=custom_imageppf)
```
## Requirements
- Python 3.x
- Tesseract OCR
- OpenCV (cv2)
- Pillow (PIL)
- pytesseract
- nltk
## Installation
- Install Python 3.x from python.org
- Install Tesseract OCR from    github.com/tesseract-ocr/tesseract
- Install required Python packages:
```bash
pip install opencv-python pillow pytesseract nltk
```
## Download my package form Python Repository
```bash
pip install DataOCREnhanceMain
```
# License
This project is licensed under the MIT License - see the LICENSE file for details.
 
