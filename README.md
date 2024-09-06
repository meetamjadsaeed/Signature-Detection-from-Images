# Signature Detection from Images

This project aims to detect and localize signatures from scanned documents or images using OpenCV and Scikit-Image libraries in Python. The system leverages image processing techniques to filter out noise and isolate signature regions based on connected components analysis.

## Features

- **Line Removal**: Horizontally and vertically removes lines from the image using OpenCV's morphological operations.
- **Thresholding**: Applies adaptive thresholding to enhance signature regions for easier detection.
- **Connected Components Analysis**: Identifies signature areas using connected component labeling from Scikit-Image.
- **Signature Bounding Boxes**: Draws bounding boxes around detected signatures and outputs a final image with the bounding boxes.
- **Signature Filtering**: Filters components based on size, only retaining those within a specified area range to reduce noise.
  
## Project Structure

```plaintext
.
├── inputs/                        # Folder for input images
│   ├── signatures/                # Folder containing signature images
│       └── in5.png                # Sample input image for signature detection
├── outputs/                       # Folder for output images
│   └── out5_final.png             # Output image with detected signatures
├── signature_detection.py         # Main Python script for signature detection
└── README.md                      # Project documentation (this file)
```

## Dependencies

The project requires the following Python libraries:

- `opencv-python`
- `matplotlib`
- `scikit-image`

You can install them using the following command:

```bash
pip install opencv-python matplotlib scikit-image
```

## How It Works

1. **Preprocessing**: 
   - The image is first converted to grayscale.
   - Morphological transformations are applied to remove horizontal and vertical lines that could interfere with signature detection.
  
2. **Thresholding**: 
   - Otsu's method is used to apply binary thresholding, inverting the image to highlight potential signatures.

3. **Connected Components Analysis**: 
   - Regions are labeled using Scikit-Image's `measure.label()` function, and components (signatures) are identified based on size constraints.
   
4. **Signature Localization**: 
   - The script draws bounding boxes around the detected signature regions and saves the output image.

## Usage

To detect signatures in an image, run the `signature_detection.py` script:

```bash
python signature_detection.py
```

Ensure that your input image is placed in the `./inputs/signatures/` directory.

## Output

- The script generates an output image (`out5_final.png`) with detected signatures highlighted by red bounding boxes.

## Improvements

- **Bounding Box Merging**: Overlapping bounding boxes could be merged to improve detection accuracy for connected signature regions.
- **Noise Reduction**: Further noise reduction techniques could be applied to eliminate any remaining artifacts from the images.
  
## Example

### Input Image

![Input Image](./inputs/signatures/in5.png)

### Output Image

![Output Image](./outputs/out5_final.png)

## License

This project is open-source and available under the MIT License.
