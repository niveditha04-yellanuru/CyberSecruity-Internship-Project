# 🔐 Cyber Security Internship Project

## Image Steganography – Secure Data Hiding Using Python

A cybersecurity project developed during an **AICTE-supported Cyber Security Internship**, demonstrating the concept of **image steganography** — hiding confidential information inside an image so that the existence of the message is not immediately apparent.

The project is implemented using **Python and OpenCV** and provides a basic mechanism for encoding a secret message into an image and retrieving the hidden message using a passcode.

---

## 📌 Project Overview

Cybersecurity focuses on protecting information from unauthorized access, modification, and disclosure.

One important area of information security is **data hiding**. Instead of transmitting confidential information as plain text, sensitive information can be concealed inside another digital medium such as an image.

This project demonstrates a simple **Image Steganography** technique in which:

1. An image is selected as the carrier.
2. The user enters a secret message.
3. A passcode is provided for authentication.
4. The message is encoded into image pixel values.
5. A new encrypted/modified image is generated.
6. The hidden message can later be extracted using the correct passcode.

---

# 🎯 Objectives

The main objectives of this project are:

* Understand fundamental cybersecurity concepts.
* Understand the concept of **data hiding**.
* Learn the basics of **image steganography**.
* Implement steganography using Python.
* Work with image pixels using OpenCV.
* Understand how information can be embedded into digital media.
* Implement password/passcode-based access control.
* Demonstrate basic secure communication concepts.
* Gain practical experience with Python-based cybersecurity applications.

---

# 🔐 What is Steganography?

**Steganography** is the practice of hiding information inside another file, such as:

* 🖼️ Image
* 🎵 Audio
* 🎥 Video
* 📄 Text
* 🌐 Network traffic

The primary objective is to hide the **existence of the communication**.

### Example

Instead of sending:

```text
Secret Message: MEET AT 10 PM
```

directly to another person, the message can be hidden inside an image.

The receiver sees an ordinary image, while the authorized user can extract the hidden message.

---

# 🖼️ Project Concept

The project uses an image as the **carrier file**.

### Encoding

```text
Original Image
      ↓
Secret Message
      ↓
Passcode
      ↓
Pixel-Level Data Hiding
      ↓
Modified Image
```

### Decoding

```text
Modified Image
      ↓
Passcode Verification
      ↓
Pixel Data Extraction
      ↓
Hidden Message
```

---

# 🛠️ Technologies Used

| Technology          | Purpose                             |
| ------------------- | ----------------------------------- |
| Python              | Core programming language           |
| OpenCV              | Image processing                    |
| OS Module           | Opening generated image files       |
| String/Data Mapping | Character-to-value conversion       |
| Pixel Manipulation  | Embedding and extracting data       |
| Git & GitHub        | Version control and project hosting |

---

# 📦 Python Libraries

The project primarily uses:

```python
import cv2
import os
import string
```

### OpenCV

OpenCV is used to:

* Read images
* Access image pixels
* Modify pixel values
* Save the modified image

### OS

The `os` module is used to open the generated image on Windows.

---

# 📂 Project Structure

```text
CyberSecruity-Internship-Project/
│
├── cyber internship-Aicet/
│   │
│   ├── 1.AICTE B4 Offer Letter.pdf
│   │
│   ├── 2.Hiding_Data.py
│   │
│   ├── 3.Project_Presentataion.pptx
│   │
│   ├── 3.mygod.jpg
│   │
│   ├── 5.AICTE B4 Certificates.pdf
│   │
│   └── skill india cyber security.pdf
│
└── README.md
```

The repository currently contains these internship/project artifacts in the `cyber internship-Aicet` directory.

---

# ⚙️ How the Project Works

## Step 1 – Import Libraries

The program starts by importing OpenCV and operating-system functionality.

```python
import cv2
import os
import string
```

---

## Step 2 – Load the Image

The carrier image is loaded using OpenCV.

```python
img = cv2.imread("path_to_image.jpg")
```

The image acts as the medium in which the secret information is stored.

> Replace the original hard-coded Windows path with the actual path to your image when running the project on another computer.

---

# Step 3 – Enter Secret Message

The user enters the confidential message:

```python
msg = input("Enter secret message:")
```

Example:

```text
Enter secret message: This is my secret message
```

---

# Step 4 – Enter Passcode

The user provides a passcode:

```python
password = input("Enter a passcode:")
```

The passcode is subsequently used for authorization during the extraction process.

---

# Step 5 – Character Mapping

The program creates dictionaries that map characters to numeric values and numeric values back to characters.

```python
d = {}
c = {}

for i in range(255):
    d[chr(i)] = i
    c[i] = chr(i)
```

Conceptually:

```text
Character → Numeric Value
Numeric Value → Character
```

This allows characters from the secret message to be represented as values that can be stored in image pixels.

---

# Step 6 – Hide the Message

The program iterates through the secret message and modifies image pixel values.

```python
for i in range(len(msg)):
    img[n,m,z] = d[msg[i]]
```

The position is changed as the program processes each character.

```python
n = n + 1
m = m + 1
z = (z + 1) % 3
```

The project therefore demonstrates the relationship between:

```text
Secret Character
        ↓
Numeric Representation
        ↓
Image Pixel
```

---

# Step 7 – Generate the Modified Image

The modified image is saved as:

```python
cv2.imwrite("encryptedImage.jpg", img)
```

This creates the output image containing the hidden information.

---

# Step 8 – Passcode Verification

Before attempting to retrieve the message, the program requests the passcode:

```python
pas = input("Enter passcode for Decryption")
```

The entered passcode is compared with the original password.

```python
if password == pas:
```

If the passcode matches, the program proceeds with message extraction.

---

# Step 9 – Extract the Hidden Message

The program reads the corresponding pixel values and converts them back into characters:

```python
message = message + c[img[n, m, z]]
```

The extracted message is then displayed:

```text
Decryption message: <hidden message>
```

If the passcode is incorrect:

```text
YOU ARE NOT auth
```

---

# 🔄 Project Workflow

```text
                 START
                   │
                   ▼
            Select Image
                   │
                   ▼
          Enter Secret Message
                   │
                   ▼
             Enter Passcode
                   │
                   ▼
        Convert Characters
        into Numeric Values
                   │
                   ▼
       Modify Image Pixel Data
                   │
                   ▼
       Save Modified Image
                   │
                   ▼
        Request Passcode
                   │
          ┌────────┴────────┐
          │                 │
       Correct            Incorrect
          │                 │
          ▼                 ▼
   Extract Message      Access Denied
          │
          ▼
     Display Message
          │
          ▼
         END
```

---

# 💻 Requirements

Before running the project, install Python.

Recommended:

```text
Python 3.x
```

Install OpenCV:

```bash
pip install opencv-python
```

Verify the installation:

```bash
python -c "import cv2; print(cv2.__version__)"
```

---

# ▶️ How to Run

## 1. Clone the Repository

```bash
git clone https://github.com/niveditha04-yellanuru/CyberSecruity-Internship-Project.git
```

## 2. Open the Project

```bash
cd CyberSecruity-Internship-Project
```

## 3. Enter the Project Folder

```bash
cd "cyber internship-Aicet"
```

## 4. Install Dependencies

```bash
pip install opencv-python
```

## 5. Update the Image Path

Open:

```text
2.Hiding_Data.py
```

Change the image path to your local image.

Example:

```python
img = cv2.imread("mygod.jpg")
```

or:

```python
img = cv2.imread(r"C:\Users\YourName\Pictures\mygod.jpg")
```

Using a raw string (`r"..."`) is recommended for Windows paths.

## 6. Run the Program

```bash
python 2.Hiding_Data.py
```

---

# 🧪 Example

### Input

```text
Enter secret message: Hello Cyber Security
Enter a passcode: 1234
```

The program processes the image and generates:

```text
encryptedImage.jpg
```

During extraction:

```text
Enter passcode for Decryption: 1234
```

Output:

```text
Decryption message: Hello Cyber Security
```

With an incorrect passcode:

```text
Enter passcode for Decryption: 5678
```

Output:

```text
YOU ARE NOT auth
```

---

# 🔒 Security Concepts Demonstrated

This project provides practical exposure to several cybersecurity concepts.

### 1. Confidentiality

The secret information is not directly visible in the carrier image.

### 2. Data Hiding

Information is embedded into image data.

### 3. Authentication

A passcode is used to control access to the hidden information.

### 4. Secure Communication

The concept can be used to demonstrate how information may be concealed during communication.

### 5. Image Security

The project demonstrates how image pixels can be manipulated programmatically.

---

# 📊 Project Components

## 1. Python Implementation

Main source file:

```text
2.Hiding_Data.py
```

This contains the implementation of the data-hiding mechanism.

## 2. Carrier Image

```text
3.mygod.jpg
```

This image is included as part of the project resources.

## 3. Project Presentation

```text
3.Project_Presentataion.pptx
```

The repository contains a project presentation associated with the internship project.

## 4. Internship Documentation

```text
1.AICTE B4 Offer Letter.pdf
```

The repository includes the AICTE internship offer documentation.

## 5. Internship Certificate

```text
5.AICTE B4 Certificates.pdf
```

The repository also contains the AICTE certificate documentation.

## 6. Skill India Certificate

```text
skill india cyber security.pdf
```

A Skill India cybersecurity certificate is also included.

---

# 🎓 Internship Learning Outcomes

Through this internship project, the following areas were explored:

* Cybersecurity fundamentals
* Information security
* Data confidentiality
* Image steganography
* Python programming
* OpenCV
* Image processing
* Pixel manipulation
* Authentication concepts
* Secure data handling
* GitHub version control
* Project documentation
* Technical presentation

---

# 🚀 Future Improvements

The current implementation is a basic educational demonstration. It can be significantly improved for a more production-oriented cybersecurity project.

### Possible improvements:

* Implement proper **LSB steganography**.
* Use stronger encryption such as **AES** before hiding the message.
* Use a cryptographic hash for password verification.
* Avoid storing plaintext passwords.
* Support larger messages safely.
* Add message-length metadata.
* Add GUI using Tkinter.
* Support PNG images to reduce compression-related data loss.
* Add image validation.
* Add error handling.
* Add file-based secret message input.
* Add encryption + steganography pipeline.
* Add a separate Encode/Decode interface.
* Add logging and security controls.
* Add automated tests.

---

# ⚠️ Security Note

This project is intended primarily for **educational and internship purposes**.

The current implementation should not be considered a production-grade secure communication system because it uses direct pixel manipulation and a simple passcode comparison rather than modern cryptographic protection.

For real-world confidential communication, the hidden message should first be encrypted using a recognized cryptographic algorithm such as AES, followed by a robust steganography technique.

---

# 📚 Key Cybersecurity Concepts

| Concept              | Description                                         |
| -------------------- | --------------------------------------------------- |
| Steganography        | Hiding information inside another medium            |
| Data Confidentiality | Protecting information from unauthorized access     |
| Authentication       | Verifying authorized access                         |
| Encryption           | Converting readable information into protected data |
| Image Processing     | Manipulating digital images programmatically        |
| Pixel Manipulation   | Accessing and modifying individual image values     |
| Secure Communication | Protecting information during transmission          |

---

# 💡 Skills Demonstrated

### Programming

* Python
* Basic algorithms
* Loops
* Dictionaries
* Conditional statements
* User input handling

### Cybersecurity

* Data hiding
* Steganography
* Authentication concepts
* Confidentiality
* Secure information handling

### Image Processing

* OpenCV
* Image loading
* Pixel access
* Pixel modification
* Image generation

### Development Tools

* Git
* GitHub
* VS Code / Python IDE

---

# 📁 Repository

**GitHub Repository:**

https://github.com/niveditha04-yellanuru/CyberSecruity-Internship-Project

**Project Folder:**

https://github.com/niveditha04-yellanuru/CyberSecruity-Internship-Project/tree/main/cyber%20internship-Aicet

---

# 👩‍💻 Author

**Niveditha Yellanuru**

Computer Science & Engineering

Interested in:

* Cybersecurity
* Data Analytics
* Python
* SQL
* Power BI
* Tableau
* Software Development

---

# ⭐ Internship Project

**AICTE Cyber Security Internship**

This repository documents the learning, implementation, presentation, and certification associated with the cybersecurity internship.

---

# 📜 Disclaimer

This project was developed for educational purposes as part of a cybersecurity internship. It demonstrates fundamental concepts of information hiding and image processing and should not be used as a replacement for professionally audited cryptographic or secure communication systems.

---

## ⭐ If you found this project useful

Consider giving the repository a ⭐ on GitHub.
