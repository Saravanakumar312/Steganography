
# Steganography Project

### Overview
This project implements a simple form of steganography, a technique used to hide secret data within a cover medium, specifically a `.bmp` image file. The program allows for encoding and decoding of secret files (e.g., `.txt`, `.doc`, etc.) into or from a BMP image. This method leverages the redundancy in the image file to embed the secret data without significantly altering the visual appearance of the image.

### Features
- **Encoding:** Hide a secret file within a BMP image.
- **Decoding:** Retrieve the secret file from a BMP image.
- **Command-Line Interface:** Interact with the program using straightforward command-line arguments.
- **Validation:** Ensures the cover image has enough capacity to store the secret file.
  
### Prerequisites
- Basic understanding of C programming.
- Familiarity with command-line operations.
- BMP image files with sufficient size to hold the secret data.

### Sample Execution
1. **For Encoding:**
   ```bash
   $ ./a.out -e beautiful.bmp secret.txt stego.bmp
   ```
   - The program will read and validate the arguments, check the capacity of the BMP image, and encode the secret file into a new image file named `stego.bmp`.

2. **For Decoding:**
   ```bash
   $ ./a.out -d stego.bmp decode.txt
   ```
   - The program will decode the hidden data from `stego.bmp` and save it as `decode.txt`.

### How It Works
- **Encoding Process:**
  - The BMP header is read and copied to the output image.
  - A magic string is embedded to identify the encoded image.
  - The secret file's extension and data are encoded into the least significant bits of the BMP image's pixels.
  
- **Decoding Process:**
  - The magic string is checked to verify if the image contains encoded data.
  - The secret file’s extension and data are extracted from the image and reconstructed into the original file.

### Usage
- **Encoding:**
  ```bash
  ./a.out -e <cover_image.bmp> <secret_file> <output_image.bmp>
  ```
  - `<cover_image.bmp>`: The BMP image used to hide the secret file.
  - `<secret_file>`: The file to be hidden.
  - `<output_image.bmp>`: The new BMP image with the hidden file.

- **Decoding:**
  ```bash
  ./a.out -d <stego_image.bmp> <output_file>
  ```
  - `<stego_image.bmp>`: The BMP image containing the hidden file.
  - `<output_file>`: The name of the file to be created from the hidden data.

### Error Handling
- The program provides feedback if there are issues with argument validation, insufficient capacity in the BMP image, or if decoding fails.

It seems like you want to include a list of files shown on the left side of your GitHub repository into your `README.md` file. Here's how you can format it:

---

### File Structure

- **beautiful.bmp**: Sample BMP image used for encoding data.
- **common.h**: Contains common functions used in both encoding and decoding processes.
- **decode.c**: Source file for decoding logic.
- **decode.h**: Header file containing function prototypes and necessary macros for decoding.
- **decode.txt**: Example output file for decoded data.
- **encode.c**: Source file for encoding logic.
- **encode.h**: Header file containing function prototypes and necessary macros for encoding.
- **secret.txt**: The secret message file used for encoding into the BMP image.
- **stego.bmp**: The output BMP image with the hidden secret message.
- **test_encode.c**: Test file used to verify encoding functions.
- **types.h**: Defines custom types and enumerations used throughout the program.


### Future Enhancements
- Support for additional image formats.
- Implementation of more robust error handling and user input validation.
- Development of a GUI for easier interaction.


