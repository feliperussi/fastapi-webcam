# FastAPI Webcam Streaming

This is a FastAPI application that streams video from a webcam. It is designed to run on a Raspberry Pi using Docker.

## Prerequisites

- Raspberry Pi with Ubuntu
- Docker installed on Raspberry Pi
- Webcam connected to Raspberry Pi

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/feliperussi/fastapi-webcam.git
cd fastapi-webcam
```

### 2. Create a Virtual Environment (Optional but Recommended)

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Required Packages

```bash
pip install -r requirements.txt
```

## Docker Setup

### 1. Build the Docker Image

Make sure you are in the project directory where the `Dockerfile` is located.

```bash
docker build -t fastapi-webcam-app .
```

### 2. Run the Docker Container

```bash
docker run -d -p 8000:8000 --name fastapi-webcam-app fastapi-webcam-app
```

## Running the Application

### 1. Start the FastAPI Application

If not using Docker, you can start the application directly:

```bash
uvicorn main:app --host 0.0.0.0 --port 8000
```

### 2. Access the Video Stream

Open a web browser on your phone or any device connected to the same network as the Raspberry Pi, and go to:

```text
http://<your_raspberry_pi_ip>:8000/video_feed
```

Replace `<your_raspberry_pi_ip>` with the actual IP address of your Raspberry Pi.

## Checking Installed Package Versions

To check the versions of the installed packages:

```bash
pip list
```

## Requirements

The `requirements.txt` file should contain the specific versions of the libraries used:

```text
fastapi==0.95.0
uvicorn==0.21.1
opencv-python-headless==4.5.3.56
```