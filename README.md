# face_recognizer
This was my work for a project in my Computer Vision course at the University of San Diego  

We used [this dataset](https://vis-www.cs.umass.edu/lfw/) for training and validation  

**Note that you need to have CMake and a C compiler to be able to install the dependencies required to run this project.**  

We recommend to create a venv with **Python 3.9** as the project might not run properly with newer Python versions.  
Be sure to install the packages in *./requirements.txt*  

The project expects this file heirarchy:


```
│   dataset_cleanup.ipynb
│
├───data
│   └───Aaron_Piersol
│   │    img1.jpg
│   │    img2.jpg
│   │
│   └───Abdoulaye_Wade
│             img1.jpg
│             img2.jpg
└───face_recognizer
    │   detector.py
    │
    ├───output
    │
    ├───training
    │
    ├───validation
```

Provided that data_cleaning script is run, the model can be trained by running the command line prompt `python detector.py --train`. The encodings are saved in *./face_recognizer/output*  
For validation, run `python detector.py --validate`  
For testing a single image, run `python detector.py --test -f img_path`. Note that if faces are detected in the picture, it will be saved in *./face_recognizer/output*  
Below is an illustration of running the --test command  

![image](https://github.com/josephbinny/face_recognizer/blob/main/face_recognizer/output/detected%7B'Aaron_Peirsol'%7D1702892481.jpg)  

You can choose the method that face-recognition library would use to perform the training and testing by specifying the argument `-m [hog, cnn]`  
cnn is optimized for GPU-enabled environments and hog (histogram of oriented gradients) works best for CPU.

You can choose run `python detector.py --help` to get a comprehensive list of command line arguments that you can use.  
