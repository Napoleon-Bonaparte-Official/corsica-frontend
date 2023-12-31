---
toc: True
comments: False
layout: post
title: Advik's Blog - CPT Warmup
type: plans
courses: {'compsci': {'week': 0}}
---

### Image Manipulation Page Creation

![alt_text](/corsica-frontend/images/advikBlog1.png)

Created a new page layout for Image Manipulation, specifically focusing on LSB (Least Significant Bit) Steganography. The HTML file includes sections for encoding and decoding messages within images. The "Encode Message" section provides an interface with an image upload option, a text input for the message to be encoded, and a button to trigger the encoding process through a JavaScript function called "encodeMessage." Similarly, the "Decode Message" section allows users to upload an image and decode a hidden message using the "decodeMessage" JavaScript function. The decoded message is displayed in a paragraph element with the id "decodedMessage." Additionally, a hidden canvas element with the id "canvas" is included for processing, although it is set to display:none, indicating that it is not visible by default on the page.

### LSB Stegonography

![alt_text](/corsica-frontend/images/advikBlog2.png)

Introduces a script for loading an image file and displaying it dynamically on the page. The JavaScript function "loadFile" is triggered by the “onchange” event of the file input element with the id "uploadImage." When a user selects an image file, the function fetches the file, creates a URL object for it, and assigns the source (src) attribute of the "output" image element (with id "output") to the newly created URL. This allows the selected image to be visually represented on the page. The commit also includes an input element for entering a message to be encoded, and it updates the HTML by adding the "width" attribute to the "output" image element, setting it to 200 pixels. 

### Encoding Functions and Processes

![alt_text](/corsica-frontend/images/advikBlog3.png)

This set of JavaScript functions is designed for image processing, specifically for encoding and decoding messages using LSB (Least Significant Bit) Steganography.

The `encodeMessage` function is called when a user wants to encode a message into an image. It retrieves the message and the selected image file, then calls the `processImage` function to handle the encoding process.

The `decodeMessage` function is used for decoding a hidden message from an image. It retrieves the selected image file and calls `processImage` with the decoding flag set to true.

The core functionality is implemented in the `processImage` function. It uses the FileReader API to read the selected image file as a data URL. Upon loading, it creates a new Image object and sets its source to the data URL. The image is then drawn onto a hidden canvas, allowing manipulation.

If the process is decoding (isDecode is true), it calls the `decode` function with the canvas context, image width, and height, updating the HTML to display the decoded message. Otherwise, it calls the `encode` function with the same parameters, effectively encoding the provided message into the image.

![alt_text](/corsica-frontend/images/advikBlog4.png)

This JavaScript code provides functions for encoding a binary message into the LSB (Least Significant Bit) of the RGB channels of an image. Here's a breakdown of each function:

1. **`encode function`**
    1. Parameters: `ctx` (canvas context), `width`, `height`, and `message`.
    2. Converts the message to binary using the `toBinary` function.
    3. Iterates through the image data, modifying the LSB of each color channel (R, G, B) with the corresponding bit from the binary message.
    4. Terminates the loop when the message is fully encoded.
    5. Puts the modified image data back onto the canvas.
2. **`setLSB function:`**
    1. Parameters: `pixel` (color channel value), and `bit` (the LSB to set).
    2. Clears the LSB of the pixel value (making it even) and sets it to the provided bit.
3. **`toBinary function:`**
    1. Parameter: `string` (the message to convert to binary).
    2. Converts each character in the string to its ASCII value in binary, ensuring each binary representation is 8 bits long.
    3.  Concatenates the binary representations of all characters.

This code essentially hides the binary message within the least significant bits of the RGB channels of each pixel in the image. The comment suggests adding a non-plaintext character after the message is done for easier decoding.

### Plans

![alt_text](/corsica-frontend/images/advikBlog5.png)
