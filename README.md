# Real-time Face Recognition and Pose Estimation with VGGFace and MediaPipe

## To run the code, please either use "Visual Studio" or "Jupyter Notebook from Anaconda Navigator".

### Thank you.

<br>

## Code Explanation:

1. **Importing Libraries**: The code imports necessary libraries including `cv2` for OpenCV operations, `os` for file operations, `numpy` for numerical computations, `mediapipe` for pose estimation, and specific modules from `keras_vggface` and `keras.preprocessing` for working with VGGFace model and preprocessing images.

2. **Loading Pose Estimation and VGGFace Models**: It loads the `Pose` model from MediaPipe for pose estimation and the VGGFace model with ResNet50 architecture (`model='resnet50'`) for feature extraction.

3. **Loading Haar Cascade Classifier**: It loads the Haar cascade classifier for face detection from OpenCV's pre-trained models.

4. **Feature Extraction**: The function `extract_features()` preprocesses and extracts features from an input image using the loaded VGGFace model.

5. **Loading Known Faces**: It iterates through the directories in the 'training_data' directory, extracts features from the first image of each person (assuming one image per person), and stores the features along with the person's name in the `known_faces` dictionary.

6. **Capturing Video and Processing Frames**: It initializes a video capture object using `cv2.VideoCapture(0)` to capture frames from the default camera (index 0). It then continuously captures frames from the video feed, converts each frame to grayscale and RGB for processing.

7. **Pose Estimation**: It performs real-time pose estimation on the captured frames using the MediaPipe `Pose` model, and draws landmarks and connections on the frame using `mp_drawing.draw_landmarks()`.

8. **Face Recognition**: It detects faces in the captured frames using the Haar cascade classifier, extracts features from the detected faces, calculates cosine similarity with known faces, and identifies the person with the minimum cosine distance. It draws rectangles around the detected faces and displays the predicted identity along with the cosine distance.

9. **Exiting**: The program exits the loop if the 'q' key is pressed, releases resources used for pose estimation and video capture, and closes all OpenCV windows.

**Key Points**:
- Utilizes VGGFace model pre-trained on ResNet50 architecture for feature extraction.
- Uses MediaPipe for real-time pose estimation.
- Loads Haar cascade classifier for face detection.
- Extracts features from known faces and stores them for recognition.
- Performs real-time face recognition and pose estimation simultaneously.
- Displays recognized faces with bounding boxes, predicted identities, and cosine distances.
- Allows quitting the application by pressing the 'q' key.
