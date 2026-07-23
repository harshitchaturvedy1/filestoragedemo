# 1-Second Video Maker

A lightweight web application that compiles 30 individual photos into a 1-second high-framerate MP4 video directly inside the browser using WebAssembly and FFmpeg.

---

## Core Value Proposition

Modern mobile devices and cameras produce high-resolution photos that consume large amounts of cloud storage. Storing rapid-fire burst shots as individual image files leads to high storage costs and high API transfer overhead.

This application solves that problem through client-side inter-frame compression:

* **Drastic Storage Reduction**: Video codecs like H.264 store full pixel data for keyframes while encoding only the changes between frames. Converting 30 JPEG files into a single 1-second MP4 can reduce total storage requirements by up to 80 percent or more.
* **Zero Server CPU Overhead**: Media processing happens locally in the user browser using FFmpeg WebAssembly. The server never bears the compute load or cost of video encoding.
* **Network Optimization**: Combining multiple image payloads into a single compressed video file reduces HTTP request overhead and speeds up cloud uploads.

---

## Features

* **Browser-Based Processing**: Files are processed entirely on the client side. No images are uploaded to external servers during conversion.
* **Storage Comparison**: Calculates and displays total raw input file size versus the final output video size in real time.
* **Motion Interpolation**: Applies frame interpolation (`minterpolate`) to create smooth transitions at 30 frames per second.
* **Frame Preview Extraction**: Pulls a sample frame from the output MP4 to confirm visual quality before downloading.

---

## Technical Stack

* **HTML5 / CSS3**: Responsive UI styling.
* **JavaScript (ES6+)**: Handles local file input, asynchronous execution, and Blob URL generation.
* **FFmpeg.js (@ffmpeg/ffmpeg v0.11.6)**: WebAssembly implementation of FFmpeg for client-side video encoding.

---

## Getting Started

1. Download or clone this repository.
2. Open `index.html` in any modern WebAssembly-enabled browser (Chrome, Firefox, Edge, Safari).
3. Select **exactly 30 images**.
4. Click **Generate 1-Second Video**.
5. View the storage savings metrics and download the resulting `1sec.mp4` file.

---

## System Requirements

* A modern web browser with WebAssembly (Wasm) support.
* An active internet connection on initial load to fetch the FFmpeg.js library from CDN.
