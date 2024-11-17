
# Real-Time Flame Detection

## Description

This project is a real-time flame detection application utilizing advanced image processing techniques. It captures frames from a camera, identifies the presence of flames, displays the results in an interactive graphical interface, and records events in a MongoDB database with encrypted connections.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Installation](#installation)
- [Execution](#execution)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Security Considerations](#security-considerations)
- [Contact](#contact)

## Overview

Flame detection is critical in various sectors such as industrial, residential, and public safety. This application provides an efficient solution for real-time flame detection, enabling quick responses to potential risks.

## Requirements

- **Python 3.6 or higher**
- **Python Libraries:**
  - `opencv-python`
  - `numpy`
  - `pymongo`
  - `certifi`
- **MongoDB Database:**
  - Access to a MongoDB server with TLS/SSL support (e.g., MongoDB Atlas)
- **Hardware:**
  - Webcam or compatible camera for video capture

## Installation

1. **Obtain the Source Code:**

   Ensure that the project files are available on your system. Copy all files to a directory of your choice.

2. **Install Dependencies:**

   Open the terminal or command prompt, navigate to the project directory, and run:

   ```bash
   pip install opencv-python numpy pymongo certifi
   ```

   Alternatively, use the `requirements.txt` file:

   ```bash
   pip install -r requirements.txt
   ```

## Execution

1. **Configure the MongoDB URI:**

   Set the `MONGODB_URI` environment variable with your MongoDB connection URI.

   On Linux/macOS:

   ```bash
   export MONGODB_URI='your_mongodb_uri'
   ```

   On Windows (Command Prompt):

   ```cmd
   set MONGODB_URI="your_mongodb_uri"
   ```

   On Windows (PowerShell):

   ```powershell
   $Env:MONGODB_URI="your_mongodb_uri"
   ```

   **Example MongoDB Atlas URI:**

   ```
   mongodb+srv://user:password@cluster0.mongodb.net/database_name?retryWrites=true&w=majority
   ```

2. **Run the Program:**

   In the terminal or command prompt, navigate to the project directory and execute:

   ```bash
   python application.py
   ```

## Usage

- **Graphical Interface:**

  - Adjust detection parameters in real-time using the sliders in the "Controls" window.
  - Click on the "Frame" window to select colors and automatically adjust color parameters.

- **Keyboard Commands:**

  - `q`: Exit the application.
  - `p`: Pause or resume the analysis.
  - `s`: Save the current parameters.
  - `c`: Capture an image of the processed frame.

## Project Structure

```
flame-detection/
│
├── application.py
├── gui_manager.py
├── image_processor.py
├── database_handler.py
├── parametros_chama.json
├── pendentes.json
├── requirements.txt
└── README.md
```

- **`application.py`**: Main file that launches the application.
- **`gui_manager.py`**: Manages the graphical user interface.
- **`image_processor.py`**: Handles image processing for flame detection.
- **`database_handler.py`**: Manages MongoDB connections and record storage.
- **`parametros_chama.json`**: Stores user-saved parameters.
- **`pendentes.json`**: Stores pending records when the MongoDB connection is lost.
- **`requirements.txt`**: Project dependency list.

## Security Considerations

- **Encrypted Connection:**
  - The application uses TLS/SSL to encrypt MongoDB connections, ensuring data security during transmission.

- **Certificate Verification:**
  - The MongoDB server certificate is verified to prevent man-in-the-middle attacks.

- **Credential Storage:**
  - The MongoDB URI should be provided via an environment variable to avoid exposing credentials in the code.

## Contact

- **Name:** Gustavo Barbosa Silva
- **Email:** gustavobsilva2003@outlook.com
