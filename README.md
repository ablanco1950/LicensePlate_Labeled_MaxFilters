# LicensePlate_Labeled_MaxFilters
From images of cars in which their license plates have been labeled, and  passing filters, their recognition is attempted by pytesseract . As there is not a single filter that works for all the licensess, it is tried with several filters and The license plate number that has been detected the most times is assigned.

To get an acceptable hit rate, you need to focus on a certain license plate format, for example the Spanish ones that usually have the NNNNAAA format. Starting from images with labels, the processing times are acceptable.

Requirements:

pytesseract

numpy

cv2

re

imutils

skimage (is scikit-image)

In the download directory you should find the downloaded test6Training.zip and must unzip folder: test6Training with all its subfolders, containing the images for the test and its labels. This directory must be in the same directory where is the program GetNumberSpanishLicensePlate_labels_MaxFilters.py ( unziping may create two directories with you name test6Training and the images may not be founded when executing it, it would be necessary copy of inner directory test6Training in the same directory where is GetNumberSpanishLicensePlate_labels_MaxFilters.py)

from the download directory, run:

GetNumberSpanishLicensePlate_labels_MaxFilters.py

That deals only with Spanish license plates with NNNNAAA format, obtaining 17 hits out of 21 records.

The evolution of the process appears on the screen with the detected license plates and as a result a file is obtained: LicenseResults.txt, with the pairs of true license plate and detected license plate.

The verification is possible because the images have been renamed with the names of the license plates of the car in the image.

Extending to the case of having to recognize all the formats of the input file, the following would be executed:

GetNumberInternationalLicensePlate_labels_MaxFilters.py

with 70 hits in the 117 plates treated

The evolution of the process appears on the screen and a file LicenseResults.txt is got 

Is also attached the module:

LicensesKaggleGetNumber_with_labels_and_filters.py

What has happened from the image files to kaggle car license plate notations downloaded from:

https://www.kaggle.com/datasets/andrewmvd/car-plate-detection

(they are downloaded in a folder called archive.zip that must be unzipped)

Detects the car license plates it interprets from each image and saves the results in the LicensesKaggleResults.txt file.

It is observed that the success rate decreases, which suggests that the filters should be adjusted to this set of Kaggle images. On the other hand, unlike 
Roboflow files that have been renamed with the car's license plate, it is not possible to automatically detect the accuracy of the results.



============================================================================================================================

Previous works that I have developed on this subject, all use the same set of images

https://github.com/ablanco1950/ablanco1950-LicensePlate_FindContours_And_Haarcascade

Instead of using the image labels framing the license plates, try to predict them using findcontours and haarcascade template.
It uses a set of filters and detects the license plate based on the license plate that has been detected the most times.
Try to correct the rectangles found by enlarging and reducing them with successive tests, with which the time spent is exaggerated..


https://github.com/ablanco1950/LicensePlate_FindContours same as above, but only use findcontours, less precise

https://github.com/ablanco1950/LicensePlate_CLAHE

Use labels and focus in Contrast Limited Adaptive Histogram Equalization (CLAHE) filters.

Produces for each processed image a code composed of two digits that identify the code used and another that identifies the treatment followed that could serve as a Y_train for a CNN or SVM, but that I have not been able to make operational

https://github.com/ablanco1950/LicensePlateImage_ThresholdFiltered is based on the fact that any car license plate image has a threshold level with which it is recognized by pytesseract.

In one of the procedures, it calculates the number plate of the car that has been found the most times varying the threshold level, and assigns it as founded.

It produces an output with the threshold level that a set of images has and implements a procedure to serve as input Y_train in an SVM, the results vary but are not satisfactory, either because as X_train a set is not used that identifies each image or because few images are used

==========================================================================================================================================================


References

https://www.roboflow.com  images an labels  from Roboflow

https://www.kaggle.com/datasets/andrewmvd/car-plate-detection images and labels from Kaggle

https://blog.katastros.com/a?ID=01800-4bf623a1-3917-4d54-9b6a-775331ebaf05

https://gist.github.com/endolith/334196bac1cac45a4893#

https://stackoverflow.com/questions/46084476/radon-transformation-in-python

https://learnopencv.com/otsu-thresholding-with-opencv/

https://towardsdatascience.com/image-enhancement-techniques-using-opencv-and-python-9191d5c30d45

https://stackoverflow.com/questions/64530229/how-do-i-get-tesseract-to-read-the-license-plate-in-the-this-python-opencv-proje

https://stackoverflow.com/questions/21324950/how-can-i-select-the-best-set-of-parameters-in-the-canny-edge-detection-algorith

https://en.wikipedia.org/wiki/Kernel_(image_processing)

https://stackoverflow.com/questions/4993082/how-can-i-sharpen-an-image-in-opencv, answer 66

https://en.wikipedia.org/wiki/Kernel_(image_processing)

https://www.sicara.fr/blog-technique/2019-03-12-edge-detection-in-opencv

https://www.aprendemachinelearning.com/clasacion-de-images-en-python/


https://www.kaggle.com/code/mclikmb4/vehicle-license-plate-detection-vgg16

Format PASCAL VOC of annotations
https://mlhive.com/2022/02/read-and-write-pascal-voc-xml-annotations-in-python#:~:text=Pascal%20VOC(Visual%20Object%20Classes,and%20train%20Machine%20Learning%20models.

Filters

https://gist.github.com/endolith/334196bac1cac45a4893#

https://stackoverflow.com/questions/46084476/radon-transformation-in-python

https://gist.github.com/endolith/255291#file-parabolic-py

https://learnopencv.com/otsu-thresholding-with-opencv/

https://towardsdatascience.com/image-enhancement-techniques-using-opencv-and-python-9191d5c30d45

https://blog.katastros.com/a?ID=01800-4bf623a1-3917-4d54-9b6a-775331ebaf05

https://programmerclick.com/article/89421544914/

https://anishgupta1005.medium.com/building-an-optical-character-recognizer-in-python-bbd09edfe438

https://datasmarts.net/es/como-usar-el-detector-de-puntos-clave-mser-en-opencv/https://felipemeganha.medium.com/detecting-handwriting-regions-with-opencv-and-python-ff0b1050aa4e

Note: On 03/13/2023, the best results are obtained with the https://github.com/ablanco1950/LicensePlate_Yolov8_Filters_PaddleOCR project, which would replace this one.
