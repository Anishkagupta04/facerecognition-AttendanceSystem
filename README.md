# facerecognition-AttendanceSystem
Introduction

This project implements a face recognition-based attendance system using OpenCV and Firebase. It leverages the power of facial recognition to mark attendance efficiently and accurately, while storing attendance data on a Firebase database.


Prerequisites

Before you begin, ensure you have the following:

Python: Installed on your system.

OpenCV: Installed and configured. You can install it using pip install opencv-python.

Required Libraries: Install necessary libraries using pip install numpy matplotlib firebase_admin.

Firebase Account: Create a Firebase account and project.

Service Account Key: Generate a service account key from your Firebase project and save it as serviceAccountKey.json.


Project Structure

facerecognition-AttendanceSystem
├── dataset
│   ├── images
│   └── labels.csv
├── main.py
├── utils.py

dataset: Contains the image dataset for training and recognition.

images: Stores the images of individuals.

labels.csv: Contains the corresponding labels for each image (e.g., names).

main.py: The main script that drives the attendance system.

utils.py: Utility functions for image processing and recognition.


Firebase Configuration

Replace the placeholder values in main.py with your Firebase project details:

Python
cred = credentials.Certificate("serviceAccountKey.json")
firebase_admin.initialize_app(cred, {
    'databaseURL': "https://your-firebase-database-url.firebaseio.com/",
    'storageBucket': "your-firebase-storage-bucket.appspot.com/images"
})

Use code with caution.

Usage

Prepare Dataset:

Create a directory named dataset with subdirectories for images and labels.csv.
Collect images of individuals and place them in the images directory.
Create a labels.csv file with columns for image filenames and corresponding names.

Train Model:

Run the main.py script with the --train flag:
Bash
python main.py --train
Use code with caution.

This will train a face recognition model using the provided dataset and save the encoded data to a pickle file.
Mark Attendance:

Run the main.py script without the --train flag:

Bash
python main.py
Use code with caution.

The system will capture a live video feed and attempt to recognize faces.

If a recognized face matches an entry in the labels.csv file, attendance will be marked and stored in the Firebase database.

Customization

Model: You can experiment with different face recognition algorithms (e.g., LBPH, Eigenfaces, Fisherfaces) by modifying the utils.py file.

Dataset: Increase the number of images per individual for better accuracy.

Performance: Adjust parameters like threshold values and image preprocessing techniques to optimize performance.

Firebase: Customize the Firebase database structure to store additional student information as needed.

RESULT

![WhatsApp Image 2024-09-04 at 11 13 57 AM](https://github.com/user-attachments/assets/ac2c56a2-f7c3-45b7-ad81-b55c20a0c24d)
![WhatsApp Image 2024-09-04 at 11 13 51 AM](https://github.com/user-attachments/assets/cc6751de-179b-4401-9958-20afc2a2ad25)
![WhatsApp Image 2024-09-04 at 11 14 05 AM](https://github.com/user-attachments/assets/524ba1c3-884c-4ef7-bb47-1d03e4bd5faf)
