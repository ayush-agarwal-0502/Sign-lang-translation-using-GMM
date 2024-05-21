# Sign-lang-translation-using-GMM

Probably my first project where I was also responsible for data collection :) 

Skills and tools - Computer Vision, Gaussian Mixture model, Mediapipe, PCA, Machine Learning, Python 

## Results - 

![final result](https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/assets/86561124/b0af9754-2f20-4934-9001-0a0ed2217e8e)

Spelt my name using ASL sign language alphabets :) 

## Data collection process - 

Used mediapipe to get hand landmarks from running webcam videostream .

Substracted first pair of coordinates from all others, so that my values only depend on the relative position of fingers rather than their position across the screen .

(Another idea that can be implemented in future is maybe getting the angles between the fingers , we know that angle between 2 lines is |m1-m2|/|1+m1m2| so we can use that )

I have only trained for 5 alphabets - A, Y, U, S, H (the alphabets in my name) since data collection would have been a long process and this was meant to be a fun project .

![asl_data_collection](https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/assets/86561124/21f41343-680c-46ac-88b7-a3e48610a274)

Here is a GIF of me collecting data 

Data Collection code - https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/blob/main/data_collector_sign_language_translator_1.ipynb

After this process I got a dataset that looked like this - 

![image](https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/assets/86561124/0f4b34ab-b644-45ea-98a5-63f2073cbbe8)

## Data Processing and Visualization - 

![image](https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/assets/86561124/dea10d5f-83af-44b2-9935-0b6bae208db4)

These are the PCA plot results of the dataset . Makes sense to me . 

Would love it if someone wants to collaborate on the data colection part and wants to collect the data for all the alphabets . Maybe we can make something nice for the deaf ppl. 

My hypothesis was that the 42 datapoints for hand would have different values for each alphabet , the values would be somewhat gaussian around the mean (where the mean represents the perfect way to hold up that alphabet in sign language) . PCA showed that my hypothesis was somewhat right . So I proceeded with training a GMM (Gaussian Mixture Model) .

Data Processing Code - https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/blob/main/model_sign_language_translator_2.ipynb

## Other things - Deployment and stuff - 

For deployment I decided that if the model was 99% or more sure about an alphabet (bcoz its a gaussian so we can easily calculate confidence wrt a prediction) then it would show an alphabet else it would show nothing . 

Also here are some other mediapipe tools I was playing with for fun, u might find it intresting - 

https://github.com/google-ai-edge/mediapipe/blob/master/docs/solutions/face_detection.md

![image](https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/assets/86561124/44b2126f-c840-4178-a125-cb2d431c39ed)

https://github.com/google-ai-edge/mediapipe/blob/master/docs/solutions/holistic.md

![image](https://github.com/ayush-agarwal-0502/Sign-lang-translation-using-GMM/assets/86561124/5d7c8eea-c4c9-49c6-9785-b3cf0f9a325a)


