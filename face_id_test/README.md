# Facial Identification Test


A basic implementation of openCV's facial identification. Mainly to play around and test the code

## Usage Guide

This guide assumes you have the necessary packages installed(if not, follow the installation instructions in the repo's main README)

- In order to encode your images for openCV, they must be in dlib format. In order to do this, you can use the *encode_face.py* file. 

- To load images for the encoder, make a folder which will contain all the images(you can use the provided `dataset` folder or make your own)
place a folder with the name of the face you would like to identify into it, and place the images into their corresponding folders

- For example, inside `datasets` I could place a folder called `rick_astley` and place images of Rick into that folder

- You also need a PICKLE file which we will store the encoded images. You can make your own or use the provided encodings.pickle

- To run the program, simply cd into the folder containing the encoder program and run `python encode_faces.py --dataset [your dataset file path here] --encodings [your file name here]`
Place the file path to the folder in which you stored all your to-be encoded images in place of [your dataset file path here] and place the file path of the PICKLE file you want the dumps to go to in place of [your file name here]

- Upon running the above code, the program will begin encoding the dataset. Keep in mind this may take anywhere from a couple seconds to a few hours depending on the amount of images to encode and whether or not GPU acceleration was enabled when building dlib(CUDA enabled GPUs only).

- After the images are encoded, you can now use recognize_faces_image.py to detect faces in images!

- To detect faces in images, you can either place the images in the `input_images` folder provided to easily find them or just use the file path of wherever the image is stored

- cd into the folder where recognize_faces_image.py is stored

- To run the detection program, run `python recognize_faces_image.py --detection-method [detection method] --image [file path] --encodings [encodings location]`

-- Replace [detection method] with either `hog` for speed or `cnn` for accuracy

-- Replace [file path] with the file path of the image you would like to use. This would be input_images/[image name] if you used the provided folder

-- Replace [encodings location] with the PICKLE file where you stored your encodings. This would be encodings.pickle if you used the provided pickle file

- And thats it! you're done, after the code detects (or fails to) a face, it will open a new window containing the image output with the faces labelled 
