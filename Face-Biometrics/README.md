# Face Biometric Steganography

## Steganography:
It is the technique of concealing the secret data in to the one of the cover files, so that no one can suspect the data apart from the sender and receiver.

## Image Steganography: 
Taking the cover object as image in steganography is known as image steganography. Generally, in this technique pixel intensities are used to hide the information.

## Biometric Steganography:
This project is divided into 6 phases:

- Feature Extraction
- Key generation
- Message Encryption
- Data Embedding
- Data Extraction
- Message Decryption


![block_diagram](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/flow-chart1.PNG)

### Step 1: Face Feature Extraction
Features extracted are :
- Left eye coordinates
- Right eye coordinates
- Face coordinates
- Centre coordinates of the face
- Centre coordinates of both the eyes

![face-img](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/flow-chart1.PNG)
![face-img](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/flow-chart1.PNG)
![face-img](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/flow-chart1.PNG)
![face-img](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/flow-chart1.PNG)
![face-img](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/flow-chart1.PNG)


### Step 2:  Key Generation
Key has generated in following ways -

- We get the coordinates of face, left eye & right eye using Haar Cascade Algo. 
- We used these coordinates to compute the distances between :- 
- Left eye coordinates and center of the face 
- Right eye coordinates and center of the face 
- Coordinates of center of both the eyes and center of the face 


#### Unique key generation :
Key= (Most Significant 2 Digits of p1) * 10 + (Least Significant 1 Digits p2)
Where,
P1 = variance of Hand points pairwise distance
P2 = standard deviation of Hand points pairwise distance

● From this unique key we will get unique pixel position to embed the secret data instead of embedding the data in sequential pixels of cover image. 

### Step 3: Message Encryption
- “Transposition Cipher” cryptography technique is applied to encrypt the original message into secret message. 
- In a transposition cipher, the order of the alphabets is re-arranged to obtain the cipher-text. 

### Step 4: Data Embedding
Steps for LSB data insertion-

- First carrier image or cover image has been read and converted in to array of bits.
- Then the secret message which is in the form of bytes/characters are converted into the “ASCII” values and then ASCII values are converted into an array of bits. 
- A unique key which has generated from hand geometric features, based on this we start embedding the secret data
- Here key will gives unique pixel position of cover image to embed the data least significant bit of particular image pixel of cover object. Here 1 pixel = 1 byte.
- Stego-image has been generated which contains secret message embedded within cover image.

Cover image: 
![Stego cover image](https://github.com/anuradha9712/Biometric-Steganography/blob/master/images/source_img.png)


### Step 5: Data Extraction
Steps for LSB data extraction-
- The extracting of the embedded data is done in opposite direction of hiding process.
- Here embedded secret data has extracted from stego-image
- While extracting secret data the hand key is used. while embedding the data we have used key to select the embedding position in cover image so while extracting also we need that key to extract secret data
- This gives complete security to the embedded data in the cover image. 

### Step 6: Message Decryption
- We have the encrypted msg. 
- Transposition Cipher Decryption technique is performed for decryption.











