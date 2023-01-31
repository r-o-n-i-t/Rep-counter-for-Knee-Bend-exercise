# Rep-counter-for-Knee-Bend-exercise

## Steps Involved:
* Setting up the Media Pipe
* Calculating Postures
* Finding Joint Coordinates:
* Calculating angles between joints
* Timer, rep counter, state (bent or relaxed), and feedback insertion

### 1. Setting up the Media Pipe:

* Install and import Mediapipe, a Google cross-platform library that provides great, ready-to-use ML solutions for computer vision problems.
* Install and import certain other requirements, such as OpenCV and NumPy, in addition to Mediapipe.

### 2. Calculating Postures
* In this state, we will estimate all of the various joints and sections of our body.
* Capture the video stream from the supplied video file.
* Recolor our picture because it should be in RGB format when we provide it to mediapipe, not the normal BGR format when we read it.
* To detect the pose, use the Pose estimation model.
* Return the image to its original BGR format.
* Draw landmarks from the video feed to do detections (e.g., nose, eyes, ears, shoulders, elbows, wrists).

### 3. Finding Joint Coordinates:
* As in the previous step, use the posture estimation model to extract landmarks using detected pose estimation.
* Calculate the rep count for knee-bending exercises by extracting the landmarks for the primary three joints: hip, knee, and ankle.

### 4. Calculating angles between joints:
* Determine whether the leg is straight or bent by calculating the angle between the hip, knee, and ankle.
* To compute the angle, we will use a trigonometric function to calculate the radians with the help of three arguments supplied to the function to calculate angle(), which are hip, knee, and ankle, and then convert radian to angle.

### 5. Timer, rep counter, state (bent or relaxed), and feedback insertion:
* If the computed angle is less than or equal to 140°, the leg state is bent; otherwise, if the calculated angle is more than 140° and the state is bent, the state is relaxed.
* A timer is used to measure the start time when the state transitions from relaxed to bent, and the end time when the state transitions from bent to relaxed. Duration is computed by subtracting the end time from the start time.
* The rep count is increased if the user can hold the leg in the bent position for 8 seconds or longer.
* Otherwise, the feedback will print "keep your knee bent" if the user is unable to remain in the bent state for more than 8 seconds.

