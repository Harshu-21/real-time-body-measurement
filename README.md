# real-time-body-measurement
Overview
This project uses Python, Mediapipe, and OpenCV to capture and estimate human body measurements from a webcam feed. The program captures key body landmarks using Mediapipe's Pose detection module and calculates measurements like shoulder width, chest width, hip width, torso length, and average leg length. The measurements are then saved to an Excel file for further use.

Features
Real-time pose detection using Mediapipe's Pose module.
Body measurement calculation using pixel-to-centimeter scaling.
Saves the captured measurements into an Excel file for later use.
Provides an adjustable camera feed for accurate positioning before measurement capture.
Requirements
Ensure you have the following dependencies installed:

Python 3.7+
OpenCV
Mediapipe
Pandas
OpenPyXL (for saving Excel files)
Install the dependencies using:

bash
Copy code
pip install opencv-python mediapipe pandas openpyxl
How It Works
The program starts a webcam feed to allow the user to position themselves properly.
After a 5-second countdown, a frame is captured for measurement.
Mediapipe detects the body landmarks, and the program calculates measurements using a scaling factor derived from a reference width in the frame.
The measurements (shoulder width, chest width, hip width, torso length, and leg length) are displayed on the captured frame.
The measurements are saved to an Excel file named body_measurements.xlsx.
Usage
Clone this repository and navigate to the project directory.
Run the script:
bash
Copy code
python body_measurement.py
Position yourself in front of the camera. The program displays a countdown on the screen.
Once the frame is captured:
Measurements are displayed on the screen.
Measurements are saved to body_measurements.xlsx.
Key Concepts
Scaling
The program uses a reference width in pixels and its real-world width in centimeters to calculate a scaling factor:

python
Copy code
scale = REFERENCE_WIDTH_CM / REFERENCE_WIDTH_PIXELS
This scale is then used to convert pixel distances to centimeters.

Measurements
The following measurements are calculated:

Shoulder Width: Distance between the left and right shoulder landmarks.
Chest Width: Same as shoulder width (can be further customized for accuracy).
Hip Width: Distance between the left and right hip landmarks.
Torso Length: Distance between the left shoulder and left hip landmarks.
Leg Length: Sum of distances between the hip, knee, and ankle for both legs.
Output
The output Excel file, body_measurements.xlsx, contains the following columns:

Shoulder Width (cm)
Chest Width (cm)
Hip Width (cm)
Torso Length (cm)
Leg Length (cm)
Customization
Adjust the Reference Width: Update REFERENCE_WIDTH_CM with the actual width of the reference object in the frame.
Modify Countdown Timer: Change the duration of the while loop controlling the countdown (start_time).
Example Output

Troubleshooting
Webcam Issues: Ensure your webcam is functional and accessible via OpenCV.
Pose Detection Errors: Verify proper lighting and camera angle for optimal Mediapipe performance.
Incorrect Scaling: Ensure the reference width is correctly measured in real-world dimensions.
Contribution
Feel free to fork this repository and contribute by:

Enhancing measurement accuracy.
Adding more body metrics.
Improving visualization and UI.
License
This project is open-source and available under the MIT License.
