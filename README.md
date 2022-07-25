# Matlab-code

%loading the video
the_Image      = imread('Seenu.jpg');
[width, height] = size(the_Image);

if width>320
the_Image = imresize(the_Image,[320 NaN]);
end

% Create a cascade detector object.
faceDetector = vision.CascadeObjectDetector();

%finding the bounding box that encloses the face on video frame
face_Location = step(faceDetector, the_Image);

% Draw the returned bounding box around the detected face.
the_Image = insertShape(the_Image, 'Rectangle', face_Location);
figure; 
imshow(the_Image); 
title('Detected face');
%(
Code used to detect face
The project is basically based on Viola Jonnes algorithm.
It is used to detect the face in various aspects like ear,nose and eyes.
I used function called cascade object detector to detect the face which is basically,
a part of the above algorithm.)
