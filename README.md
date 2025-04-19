
VenueFlow AI - Real-Time Crowd Monitoring System 🚨📷

VenueFlow AI is a dual-camera, AI-powered crowd monitoring solution designed for real-time facial detection, people counting, alerting, and database logging. It's built using OpenCV, YOLOv8, Twilio, and an SQLPlus-compatible backend.

-----------------------------------------------------
FEATURES
-----------------------------------------------------
🎯 YOLOv8 Face Detection – Accurate and fast detection
🔥 Dual Camera Support – Monitor two webcams simultaneously
🚨 Twilio Alerts – Get real-time SMS notifications when crowd thresholds are exceeded
🗃️ Database Logging – All alerts are stored in a SQLPlus-compatible database (e.g., Oracle)
🧠 Threshold Control – Set your own limits for crowd alerts

-----------------------------------------------------
TECHNOLOGY STACK
-----------------------------------------------------
Component          | Tech Used
-------------------|-----------------------------------
Language           | Python 3.x
Face Detection     | YOLOv8 via Ultralytics
Video Processing   | OpenCV
SMS Alerts         | Twilio
Database           | SQLPlus-compatible (Oracle) via cx_Oracle
UI/Monitoring      | OpenCV GUI Window

-----------------------------------------------------
GETTING STARTED
-----------------------------------------------------
1. Clone the Repository

git clone https://github.com/your-username/venueflow-ai.git
cd venueflow-ai

2. Install Dependencies

pip install -r requirements.txt

3. Configure Credentials

Create a config.py file in the root directory and add the following:

# config.py
DB_USER = 'your_db_user'
DB_PASSWORD = 'your_db_password'
DB_DSN = 'hostname:port/service_name'

TWILIO_ACCOUNT_SID = 'your_sid'
TWILIO_AUTH_TOKEN = 'your_token'
TWILIO_FROM_NUMBER = '+1234567890'
ALERT_TO_NUMBER = '+911234567890'

4. Prepare YOLO Model

Ensure yolov8n.pt is downloaded and placed in the root directory.
Download from: https://github.com/ultralytics/ultralytics

-----------------------------------------------------
SAMPLE ORACLE DB TABLE SCHEMA
-----------------------------------------------------
CREATE TABLE crowd_alerts (
    id NUMBER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    camera_id NUMBER,
    detected_faces NUMBER,
    threshold NUMBER,
    alert_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-----------------------------------------------------
RUN THE SYSTEM
-----------------------------------------------------
python main.py

-----------------------------------------------------
WHAT IT DOES
-----------------------------------------------------
- Detects faces using YOLOv8
- Displays real-time video from 2 cameras side-by-side
- Overlays the face count on each feed
- Highlights frames with a red border when threshold exceeded
- Sends SMS alert using Twilio (with cooldown to avoid spam)
- Logs each threshold breach to the database

-----------------------------------------------------
SAMPLE OUTPUT
-----------------------------------------------------
[ALERT 🚨] Camera 1: 7 faces detected!
[ALERT SENT] SID: SMxxxxxxxxxxxxxxxxxxxxxxxxxxxx
[DB LOG] Alert logged successfully

-----------------------------------------------------
CONTACT
-----------------------------------------------------
For issues or questions, open an Issue or reach out:

Email: your.email@example.com
Twitter: @yourhandle

-----------------------------------------------------
LICENSE
-----------------------------------------------------
This project is licensed under the MIT License – see the LICENSE file for details.
