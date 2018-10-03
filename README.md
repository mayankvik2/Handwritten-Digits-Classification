Handwritten-Digits-Classification of Optical Character Recognition using HOG + SVM.Following below steps followed for buliding pipleline of opencv image classification
 
Step1:Preprocessing
Aligning digits before building a classifier similarly for producing superior results using variation in slant of their writing of    different people.Preprossing step in OpenCV will fix this vertical slant by deskewing of grayscale images by calculating image moments.
 	m = cv2.moments(img)
  skew = m['mu11']/m['mu02']

Step2:Calculate the Histogram of Oriented Gradients (HOG) descriptor
Histogram of oriented gradients (HOG) is a feature descriptor used to detect objects in computer vision and image processing. The HOG descriptor technique counts occurrences of gradient orientation in localized portions of an image
Parameters used for HOG descriptor in OpenCV:
 wineSize: wineSize choosen is 20×20 because the size of the digit images in our dataset is 20×20
 cellSize: CellSize choosen is 8×8 based on the scale of the features
 blockSize: BlockSize choosen is 8×8  for best results.
 nbins: nbins choosen is recommended value of 9 to capture gradients between 0 and 180.
   
Step3:Training SVM Model:
Used Support Vector Machines (SVM) for Classification.SVM works as Maximal-Margin Classifier with a hyperplane that splits the input variable space. The hyperplane is selected to best separate the points in the input variable space by their class.
Parameter used in SVM training:
  C Parameter that defines amount of violation of the margin allowed. At C=0 is no violation and larger the value of C the more        violations of the hyperplane are permitted.The smaller the value of C, the more sensitive the algorithm is to the training data (higher variance and lower bias) but The larger the value of C, the less sensitive the algorithm is to the training data (lower   variance and higher bias). 

Results:
After training and some hyperparameter optimization, classifier hit 98.6% accuracy on digits classification.


   
