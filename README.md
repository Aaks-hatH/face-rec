# Face Recognition System

A real-time browser-based face recognition application that allows you to register faces and recognize them using your webcam.

**Built by Aakshat Hariharan**

## Features

- **Register Mode**: Capture and register faces with names
- **Recognize Mode**: Real-time face detection and recognition with confidence scores
- **Live Preview**: Visual overlay showing detection boxes and recognition results
- **Face Management**: View all registered faces with timestamps and delete capability
- **Responsive Design**: Works on desktop and mobile devices
- **No Backend Required**: Runs entirely in the browser using client-side AI

## Technology Stack

- **Face-API.js** (@vladmandic/face-api): Neural network-based face detection and recognition
- **Pure HTML/CSS/JavaScript**: No frameworks required
- **WebRTC**: Browser camera access via getUserMedia API

## How to Use

### Setup

1. Save the HTML file to your computer
2. Open it in a modern web browser (Chrome, Firefox, Edge, Safari)
3. Wait for AI models to load (happens automatically on page load)

### Register Mode

1. Click **"Start Camera"** to activate your webcam
2. Enter a name in the text field
3. Position your face clearly in front of the camera
4. Click **"Capture and Register"**
5. The system will detect your face and save it with your name

### Recognize Mode

1. Switch to **"Recognize Mode"** using the top buttons
2. Click **"Start Camera"**
3. The system will automatically detect and recognize faces in real-time
4. Recognized faces show:
   - **Green box**: Known face with name and confidence percentage
   - **Red box**: Unknown face
   - **Orange box**: Face detected but no faces registered yet

### Managing Faces

- View all registered faces in the right panel
- See registration timestamps
- Delete faces individually using the "Delete" button
- Face count badge shows total registered faces

## Model Loading

The application automatically loads three AI models on startup:

- **TinyFaceDetector**: Fast face detection
- **FaceLandmark68Net**: Facial landmark detection
- **FaceRecognitionNet**: Face recognition and descriptor generation

Models are loaded from CDN (jsDelivr) and cached by the browser.

## Browser Compatibility

- **Chrome/Edge**: Full support ✅
- **Firefox**: Full support ✅
- **Safari**: Full support ✅ (iOS may require HTTPS)
- **Opera**: Full support ✅

**Note**: HTTPS is required for camera access on most browsers (except localhost).

## Privacy & Security

- All processing happens locally in your browser
- No data is sent to external servers
- Face data is stored only in browser memory
- Data is lost when you refresh or close the page
- Camera access requires user permission

## Technical Details

### Recognition Algorithm

- Uses 128-dimensional face descriptors
- Euclidean distance matching with 0.6 threshold
- Lower distance = better match
- Confidence displayed as percentage: `(1 - distance) × 100%`

### Performance

- Detection runs at ~5 FPS (200ms interval)
- TinyFaceDetector optimized for speed over accuracy
- Video resolution: 640×480 (ideal)

### Limitations

- Faces must be clearly visible and well-lit
- Works best with frontal faces
- Multiple faces can be detected simultaneously
- Recognition accuracy depends on image quality and lighting

## Troubleshooting

**"Failed to load models"**
- Check your internet connection
- Models load from CDN, ensure it's not blocked

**"Camera error"**
- Grant camera permissions in browser settings
- Ensure no other application is using the camera
- Try refreshing the page

**"No face detected"**
- Improve lighting conditions
- Face the camera directly
- Move closer or farther to adjust distance
- Remove glasses or hats if causing issues

**Recognition not working**
- Register faces in good lighting conditions
- Ensure clear, frontal face captures
- Try re-registering with better image quality

## Future Enhancements

Possible improvements for this project:

- Local storage persistence (localStorage)
- Export/import face database
- Multiple face registration per person
- Advanced detection options (confidence threshold adjustment)
- Photo upload support
- Statistics and analytics
- Dark mode theme

## License

This project uses the Face-API.js library by Vladimir Mandic, which is licensed under MIT.

## Credits

- **Developer**: Aakshat Hariharan
- **Face Detection Library**: @vladmandic/face-api
- **Model Architecture**: Based on face-api.js by Vincent Mühler

## Support

For issues or questions about the Face-API.js library, visit:
- GitHub: https://github.com/vladmandic/face-api
- Documentation: https://vladmandic.github.io/face-api/

---

**Enjoy building with Face Recognition! **
