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
Step by step process  
# At first the things to detected should be loaded, then the size of the image should be known by size function
## The image should be resized to the if width is greater the 320 it can be done using imresize function
### Face detection can be done by using vision.CascadeObjectDetector() function,
#### Things to be detected and image detection spot shape should be mentioned.
##### Atlast image output is detected


Code used to detect face
The project is basically based on Viola Jonnes algorithm.
It is used to detect the face in various aspects like ear,nose and eyes.
I used function called cascade object detector to detect the face which is basically,
a part of the above algorithm.)
