# LicensePlate_Labeled_MaxFilters
From images of cars in which their license plates have been labeled, and  passing filters, their recognition is attempted by pytesseract . As there is not a single filter that works for all the licensess, it is tried with several filters and The license plate number that has been detected the most times is assigned.

To get an acceptable hit rate, you need to focus on a certain license plate format, for example the Spanish ones that usually have the NNNNAAA format. Starting from images with labels, the processing times are acceptable.

Requirements:

pytesseract

numpy

cv2

you

re

imutils

skimage (is scikit-image)

In the download directory you should find the downloaded test6Training.zip and must unzip folder: test6Training with all its subfolders, containing the images for the test and its labels. This directory must be in the same directory where is the program GetNumberSpanishLicensePlate_labels_MaxFilters.py ( unziping may create two directories with you name test6Training and the images may not be founded when executing it, it would be necessary copy of inner directory test6Training in the same directory where is LicensePlateFindContours.py)

from the download directory, run:

GetNumberSpanishLicensePlate_labels_MaxFilters.py

That deals only with Spanish license plates with NNNNAAA format, obtaining 17 hits out of 21 records.

The evolution of the process appears on the screen with the detected license plates and as a result a file is obtained: LicenseResults.txt, with the pairs of true license plate and detected license plate.

The verification is possible because the images have been renamed with the names of the license plates of the car in the image, although the verification is only done once the result is obtained

Extending to the case of having to recognize all the formats of the input file, the following would be executed:

GetNumberInternationalLicensePlate_labels_MaxFilters.py

with 70 hits in the 117 plates treated

The evolution of the process appears on the screen and a file LicenseResults.txt is got 

Previous works that I have developed on this subject, all use the same set of images

https://github.com/ablanco1950/ablanco1950-LicensePlate_FindContours_And_Haarcascade

Instead of using the image labels framing the license plates, try to predict them using findcontours and haarcascade template.
It uses a set of filters and detects the license plate based on the license plate that has been detected the most times.
Try to correct the rectangles found by enlarging and reducing them with successive tests, with which the time spent is exaggerated..

Produces for each processed image a code composed of two digits that identify the code used and another that identifies the treatment followed that could serve as a Y_train for a CNN or SVM, but that I have not been able to make operational

https://github.com/ablanco1950/LicensePlate_FindContours same as above, but only use findcontours, less precise

https://github.com/ablanco1950/LicensePlateImage_ThresholdFiltered is based on the fact that any car license plate image has a threshold level with which it is recognized by pytesseract.

In one of the procedures, it calculates the number plate of the car that has been found the most times varying the threshold level, and assigns it as founded.

It produces an output with the threshold level that a set of images has and implements a procedure to serve as input Y_train in an SVM, the results vary but are not satisfactory, either because as X_train a set is not used that identifies each image or because few images are used
