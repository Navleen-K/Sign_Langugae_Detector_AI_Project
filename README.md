Sign Language Detector AI Project
Real-time recognition of American Sign Language (ASL) fingerspelling from a webcam, running entirely in Google Colab. Hold up a letter sign and the project types it out. String letters together to build words and sentences.

Features
- Live webcam detection inside the Colab page, with the hand landmarks drawn over the video
- Hold-to-type: hold a sign for about a second to add that letter
- Word and sentence building: take your hand out of view to add a space
- Backspace, Clear and Speak (reads the typed text aloud) buttons
- Trains in about 10 minutes the first time, then loads the saved model from Google Drive
- Small and fast: no GPU needed


How it works:-
- MediaPipe HandLandmarker finds 21 key points on the hand in each frame.
- The points are shifted so the wrist is the origin and scaled to a common size, so the result does not depend on where the hand is or how big it looks.
- A Random Forest trained on those 63 numbers predicts the letter.
- A short smoothing window and a hold timer turn the stream of predictions into typed text.

Dataset
American Sign Language Alphabet Dataset from Mendeley Data (DOI: 10.17632/jdyksv2jhh.1), licensed under CC BY 4.0. It has Train and Test folders with one subfolder per letter.
