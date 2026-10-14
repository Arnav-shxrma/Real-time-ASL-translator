Real-Time ASL Translator (Edge AI, Vibe Coded)

This is our sign language recognition project, built by a team of 10 and presented to our board. It reads American Sign Language letters (A to Z) live from a webcam and spells them out as words on screen.

Why we built it: many people who use sign language can't easily communicate with people who don't know it. Because camera video of a person is sensitive, we chose an Edge AI approach: everything runs on the device itself, so nothing is uploaded, it responds instantly, and it needs no internet. It was also a demanding test of how far vibe coding can take a project that spans computer vision, model training, deployment and interface design.

How it works: the webcam captures video, MediaPipe Hands finds 21 hand landmarks, and these are smoothed, centred, scaled and redrawn as a clean skeleton. A custom CNN (about 308,602 parameters, trained from scratch in TensorFlow/Keras) classifies the skeleton into one of 26 letters. The model is exported to ONNX and runs in real time on CPU with ONNX Runtime. J and Z, which are movements, are handled by a motion tracker.

Technologies: Python, MediaPipe, TensorFlow/Keras, ONNX Runtime, OpenCV, NumPy, and three public Kaggle ASL datasets.

How it was built: the code was vibe coded with AI assistance and then verified by the team. Our first version reported 97.9% accuracy but struggled on a live webcam because of a leaky validation split. We rebuilt the pipeline and now report an honest 93.7% accuracy on an unseen signer (96.8% validation).

Use cases: accessibility tools, ASL learning and practice, help desks and kiosks, and a base for fuller sign language translation.

Topics: asl sign-language-recognition edge-ai mediapipe onnx tensorflow cnn computer-vision opencv real-time accessibility python vibe-coding
