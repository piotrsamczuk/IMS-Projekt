# Image Processing with Orthogonal Expansions

## Project Overview
This project implements various image processing techniques using orthogonal expansions, specifically focusing on the Discrete Fourier Transform (DFT) and Wavelet transforms. The application provides tools for filtering, transforming, and visualizing images in both spatial and frequency domains.

## Authors
- Kacper Rogalewski
- Piotr Samczuk

## Features

### Frequency Domain Operations
- Fast Fourier Transform (FFT) implementation
- Visualization of frequency domain representation
- Various frequency domain filters:
  - Low-pass filters: Ideal, Gaussian, Butterworth, Chebyshev
  - High-pass filters: Ideal, Gaussian
  - Band-pass and notch filters

### Wavelet Transform
- Haar wavelet transform implementation
- Wavelet-based image decomposition and reconstruction
- Different shrinkage methods:
  - Hard shrinkage
  - Soft shrinkage
  - Garrot shrinkage

### Image Processing Utilities
- Histogram generation and visualization
- Image enhancement techniques
- Built-in spatial domain filters:
  - Identity filter
  - Blur filter
  - Gaussian blur
  - Sharpening filter

## Technical Details

### Implementation Structure
The project is organized into several modules:
- `FFT.hpp`: Custom FFT implementation
- `fft_filters.hpp`: Frequency domain filter implementations
- `helpers.hpp`: Utility functions for image display and management
- `image_processing.hpp`: Core image processing functions
- `wavelets.hpp`: Wavelet transform implementation

### Dependencies
- OpenCV (Computer Vision library)
- C++20 standard

### Building the Project
The project uses CMake for building. To compile:

```bash
mkdir build
cd build
cmake ..
make
```

## Usage
Run the executable from the build directory:

```bash
./IMS
```

The application provides an interactive menu allowing you to:
1. View wavelet decomposition of the input image
2. Visualize the frequency domain representation
3. Apply various filters with adjustable parameters
4. View histograms of original and processed images

### Filter Selection
When prompted, select a filter type (1-8):
1. Ideal Low-Pass
2. Gaussian Low-Pass
3. Ideal High-Pass
4. Gaussian High-Pass
5. Band-Pass
6. Notch
7. Butterworth Low-Pass
8. Chebyshev Low-Pass

For some filters, you'll need to specify additional parameters:
- `D0`: Cutoff frequency (range 0-100 recommended)
- `n`: Order for Butterworth and Chebyshev filters (typical values: 1-5)
- `epsilon`: Ripple factor for Chebyshev filter (typical values: 0.1-0.5)

## Theory Background

### Orthogonal Expansions
The project focuses on orthogonal expansions used in image processing:

1. **Fourier Transform**: Decomposes an image into its frequency components, allowing for frequency-based filtering and analysis.

2. **Wavelet Transform**: Represents an image in terms of wavelets, providing both frequency and spatial information, useful for multi-resolution analysis.

### Frequency Domain Filtering
Frequency domain filtering allows for effective noise reduction, edge enhancement, and image compression by manipulating specific frequency components.

### Wavelet Applications
Wavelets are particularly useful for:
- Image compression
- Feature extraction
- Multi-resolution analysis
- Noise reduction with edge preservation

## Future Improvements
- Command-line arguments for input image selection
- Live preview of parameter changes
- Additional wavelet families (beyond Haar)
- More advanced reconstruction techniques
- Batch processing capabilities
