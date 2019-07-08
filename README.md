Captured two pictures of the same scene using different viewpoints and then, the corresponding points were matched to
obtain the disparity map of the scene. SIFT, FAST & FREAK, and AGAST & FREAK were used to find the keypoints and
descriptors. RMSE values were found to analyze the performance of the above mentioned methods.

Objective: To find Stereo Correspondence using ‘FAST+FREAK’ & ‘AGAST+FREAK’ & ‘SIFT’.

Hardware and softwares used:
System: Windows 10
Opencv: Opencv 3.3
Visual Studio : Microsoft Visual studio 2015

Description:
We have captured two photos of the same scene using different viewpoints, and then matched
the corresponding points to obtain the Disparity map of the scene. To do this we follow these
following methods to find the initial parameters i.e. keypoints and Descriptors and so on.

1. FAST+FREAK
We have used FAST (Features from Accelerated Segment Test) to detect Keypoint (Interest
point) detectors. We have then used the FREAK (Fast Retina Keypoint) to find the Feature
Descriptors. After finding the Keypoints and their corresponding Descriptors we opt to use the
best method to match these Descriptors in two images. We are using Bruteforce method for
matching the descriptors here. The matcher takes the descriptor of one feature in first set and is
matched with all other features in second set using some distance calculation. And the closest one is
returned.
Here, For BF matcher, first we have created the BFMatcher object using cv2.BFMatcher() . For the
the optional parameter, we have given cv2.NORM_L2 as normType.
Then we have found the distance between the keypoints in left image(img_1) and right
image(img_2) using the norm function. In the same loop which iterates till it reaches the length of the
‘matches’(variable), we have also calculated the highest distance(max1).
In the next for loop the calculated distance for any two keypoints will be normalized by the highest
distance(max1) and then assigned to a new image(newimg) with respect to the (x,y) coordinates of
left image. This image is created by us with zeros as pixel intensities for an image size of the original
image(left or right).
For calculating the MSE error, we take the average of squared errors between the keypoints in
newimg and the corresponding actual ground truth image(img_3) points. Taking a root of MSE
results in RMSE.
Later, we keep a count of ‘res1’ which are higher than 20.
We output the output matched image(left and right image stacked in one image) into
‘matchesimage.png’ and RMSE value into ‘ RMSE.txt ’ and the incorrectly matched points will be
calculated and printed into ‘ incorrectlymatchedpts.txt ’ in the “data folder” .

Note: The input files which are left and right images and ground truth image are taken from data
folder since the code was written that way. The outputs get printed in data folder. The data folder is
with the test.sln in each of the three folders( 1. FAST+FREAK, 2. AGAST+FREAK, 3. SIFT ).
But the sample outputs and inputs were also present in the output and input folder respectively.

2. AGAST+FREAK
We have used AGAST (Adaptive and Generic Accelerated Segment Test) to detect Keypoint
(Interest point) detectors. We have then used the FREAK (Fast Retina Keypoint) to find the
Feature Descriptors. After finding the Keypoints and their corresponding Descriptors we opt to
use the best method to match these Descriptors in two images. We are using Bruteforce
method for matching the descriptors here. The matcher takes the descriptor of one feature in first
set and is matched with all other features in second set using some distance calculation. And the
closest one is returned.
Here, For BF matcher, first we have created the BFMatcher object using cv2.BFMatcher() . For the
the optional parameter, we have given cv2.NORM_L2 as normType.
Then we have found the distance between the keypoints in left image(img_1) and right
image(img_2) using the norm function. In the same loop which iterates till it reaches the length of the
‘matches’(variable), we have also calculated the highest distance(max1).
In the next for loop the calculated distance for any two keypoints will be normalized by the highest
distance(max1) and then assigned to a new image(newimg) with respect to the (x,y) coordinates of
left image. This image is created by us with zeros as pixel intensities for an image size of the original
image(left or right).
For calculating the MSE error, we take the average of squared errors between the keypoints in
newimg and the corresponding actual ground truth image(img_3) points. Taking a root of MSE
results in RMSE.
Later, we keep a count of ‘res1’ which are higher than 20.
We output the output matched image(left and right image stacked in one image) into
‘matchesimage.png’ and RMSE value into ‘ RMSE.txt ’ and the incorrectly matched points will be
calculated and printed into ‘ incorrectlymatchedpts.txt ’ in the “data folder” .
Note: The input files which are left and right images and ground truth image are taken from data
folder since the code was written that way. The outputs get printed in data folder. The data folder is
with the test.sln in each of the three folders( 1. FAST+FREAK, 2. AGAST+FREAK, 3. SIFT ).
But the sample outputs and inputs were also present in the output and input folder respectively.

3. SIFT
We have used SIFT to find the keypoints and descriptors. After finding the Keypoints and their
corresponding Descriptors we opt to use the best method to match these Descriptors in two
images. We are using Bruteforce method for matching the descriptors here. The matcher takes
the descriptor of one feature in first set and is matched with all other features in second set using
some distance calculation. And the closest one is returned.
Here, For BF matcher, first we have created the BFMatcher object using cv2.BFMatcher() . For the
the optional parameter, we have given cv2.NORM_L2 as normType.
Then we have found the distance between the keypoints in left image(img_1) and right
image(img_2) using the norm function. In the same loop which iterates till it reaches the length of the
‘matches’(variable), we have also calculated the highest distance(max1).
In the next for loop the calculated distance for any two keypoints will be normalized by the highest
distance(max1) and then assigned to a new image(newimg) with respect to the (x,y) coordinates of
left image. This image is created by us with zeros as pixel intensities for an image size of the original
image(left or right).
For calculating the MSE error, we take the average of squared errors between the keypoints in
newimg and the corresponding actual ground truth image(img_3) points. Taking a root of MSE
results in RMSE.
Later, we keep a count of ‘res1’ which are higher than 20.
We output the output matched image(left and right image stacked in one image) into
‘matchesimage.png’ and RMSE value into ‘ RMSE.txt ’ and the incorrectly matched points will be
calculated and printed into ‘ incorrectlymatchedpts.txt ’ in the “data folder” .
Note: The input files which are left and right images and ground truth image are taken from data
folder since the code was written that way. The outputs get printed in data folder. The data folder is
with the test.sln in each of the three folders( 1. FAST+FREAK, 2. AGAST+FREAK, 3. SIFT ).
But the sample outputs and inputs were also present in the output and input folder respectively.
Conclusion : The best RMSE values come from these methods in this order SIFT, FAST & FREAK,
and then AGAST & FREAK. It is to be noted that AGAST & FREAK and FAST & FREAK have
almost similar performance.


