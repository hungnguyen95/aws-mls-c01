# 17. Rekognition

- Computer vision
- Object and scene detection
    - Can use your own face collection
- Image moderation
- Facial analysis
- Celebrity recognition
- Face comparison
- Text in image
- Video analysis
    - Objects / people / celebrities marked on timeline
    - People Pathing

---

## Rekognition: The Nitty Gritty

- Images come from S3, or provide image bytes as part of request
    - S3 will be faster if the image is already there
- Facial recognition depends on good lighting, angle, visibility of eyes, resolution
- Video must come from Kinesis Video Streams
    - H.264 encoded
    - 5-30 FPS
    - Favor resolution over framerate
- Can use with Lambda to trigger image analysis upon upload

---

## New in 2020: Rekognition Custom Labels

- Train with a small set of labeled images
- Use your own labels for unique items
- Example: the NFL (National Football League in the US) uses custom labels to identify team logos, pylons, and foam fingers in images.