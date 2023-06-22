# Facial Detection Webcam Display Streamlit App

This repository contains a Python script that creates a Streamlit application for displaying the webcam feed and performing facial detection using OpenCV. The application provides a simple interface to view the live video stream and includes a stop button to halt the feed.

## Installation

To run the application, you need to have Python and the required libraries installed. Follow the steps below to set up the environment:

1. Clone this repository to your local machine or download the script file (`main.py`) directly.

2. Install the necessary dependencies by running the following command:
   ```
   pip install streamlit opencv-python numpy
   ```

## Usage

Once you have the dependencies installed, you can launch the Streamlit app by executing the script:

```
streamlit run main.py
```

This will start the application and open it in your default web browser. The app interface will display the webcam feed in real-time, with the option to stop the feed by clicking the "Stop" button.

## How it Works

The script uses the Streamlit and OpenCV libraries to create the application. Here's an overview of the code's functionality:

1. The script sets the page title of the Streamlit app using `st.set_page_config()`.

2. The app's title and caption are displayed using the `st.title()` and `st.caption()` functions, respectively.

3. Video frames are captured from the webcam using `cv2.VideoCapture()`, with the default webcam index (0). The frames are accessed through the created `cap` object.

4. A placeholder is created using `st.empty()` to display the webcam feed.

5. A stop button is added to the app interface using `st.button("Stop")`. Clicking this button will stop the webcam feed and exit the application.

6. The script enters a while loop to continuously read frames from the webcam using `cap.read()`. If a frame is successfully retrieved, it is converted from BGR to RGB format using `cv2.cvtColor()` to match Streamlit's expected image format.

7. The converted frame is displayed in the placeholder using `frame_placeholder.image()`. The `channels="RGB"` argument specifies the color channels of the image.

8. The loop continues until the webcam feed ends (`cap.isOpened()` returns `False`) or the stop button is pressed (`stop_button_pressed` is `True`).

9. Once the loop ends, the webcam capture is released using `cap.release()` and any open OpenCV windows are closed using `cv2.destroyAllWindows()`.

## Contributing

Contributions to this repository are welcome. If you encounter any issues or have suggestions for improvements, please open an issue or submit a pull request.

## Example Screenshot
![image](https://github.com/petermartens98/Streamlit-OpenCV-Webcam-Display-Web-App/assets/87671757/c4eff4c5-e310-46c1-9b0f-ec3aa87cb463)
