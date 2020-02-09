# Biometric-Steganography

## Steganography:
It is the technique of concealing the secret data in to the one of the cover files, so that no one can suspect the data apart from the sender and receiver.

## Image Steganography: 
Taking the cover object as image in steganography is known as image steganography. Generally, in this technique pixel intensities are used to hide the information.

## Biometric Steganography:
This project is divided into 4 phases:
- Feature Extraction
- Key generation
- Data Embedding
- Data Extraction 

### Step 1: Feature Extraction
Here hand geometric features are extracted by following 3 steps.
- Image Acquisition
- Image preprocessing    
- Feature Extraction

#### Image preprocessing
- convert the colour image into the black and white image 
- unnecessary part of the captured hand image has cropped 
- Gaussian filter had used to remove the background noise of the image 
- Binary Image by Otsu Thresholding

#### Feature Extraction
- Trace contours of image used to plot all the contours point and find convex hull 
- Find tip points
- Find centre point of the hand 
- Euclidean distance is calculated between tip points & center point of hand image.

### Step 2:  Key Generation
Key has generated in four ways -

- From extracted features, tip points are located
- Pairwise distance has calculated using Euclidean distance.
- Variance has calculated for pairwise distance
- And lastly unique key has generated using variance result 

#### Unique key generation :
Key= (Most Significant 2 Digits of p1) * 10 + (Least Significant 1 Digits p2)
Where,
P1 = variance of Hand points pairwise distance
P2 = standard deviation of Hand points pairwise distance

● From this unique key we will get unique pixel position to embed the secret data instead of embedding the data in sequential pixels of cover image. 

### Step 3: Data Embedding
Steps for LSB data insertion-

- First carrier image or cover image has been read and converted in to array of bits.
- Then the secret message which is in the form of bytes/characters are converted into the “ASCII” values and then ASCII values are converted into an array of bits. 
- A unique key which has generated from hand geometric features, based on this we start embedding the secret data
- Here key will gives unique pixel position of cover image to embed the data least significant bit of particular image pixel of cover object. Here 1 pixel = 1 byte.
- Stego-image has been generated which contains secret message embedded within cover image

### Step 4: Data Extraction
Steps for LSB data extraction-
- The extracting of the embedded data is done in opposite direction of hiding process.
- Here embedded secret data has extracted from stego-image
- While extracting secret data the hand key is used. while embedding the data we have used key to select the embedding position in cover image so while extracting also we need that key to extract secret data
- This gives complete security to the embedded data in the cover image. 









