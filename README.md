# 114-ML-Group37
This is a source code of our ML Final Project - Captcha Recognition by CNN
Here is the tutorial to use.

## Dataset:
### Option 1: Download the dataset 
Kaggle link: https://www.kaggle.com/datasets/hoson09/overlap-dataset
Here we have 3 folder on this dataset.
#### (1) Test: 5000 images
#### (2) Validate: 5000 images -> Separated to 20000 single character images
#### (3) Train: 25000 images -> Separated to 100000 single character images  

### Option 2: Generate the dataset by "data_generate.ipynb"
You can also generate the dataset by yourself. Here the tutorial
#### (1) Module install
For module import. You have to ensure you have installed all the module you needed.
Run "pip install -r requirements.txt" to install all the modules. Also make sure you have download the "DroidSansMono.ttf" and "yolov9_2" to the directory.

#### (2) Module (library) import
Run the following cell to import the modules
![image](https://github.com/user-attachments/assets/9f659b4c-40d4-4127-981b-a3d585089590)

#### (3) Self-made ImageCaptcha
Run the following cell to initialize the "Self-made ImageCaptcha"
![image](https://github.com/user-attachments/assets/db9d3630-fa59-4ae7-b304-1cbdc5e2b53f)
Then you can run the following cell to test the function
![image](https://github.com/user-attachments/assets/57728907-9ba3-47f8-9364-2ab61e12fc43)
Example generated image:
![image](https://github.com/user-attachments/assets/87575edb-f895-469f-9791-06b0aeb5edd3)

#### (4) Data Preprocessing
Run the following cell to initialize the "Data Preprocessing" functions.
![image](https://github.com/user-attachments/assets/4edb7dc9-8ff4-459d-b60b-1be86d212c3e)
Then you can run the following cell to test the function
Note: Remember to change the image's path at <line 11> for testing purpose.
![image](https://github.com/user-attachments/assets/a0a09a37-8640-4447-8311-e11034769bc6)
Example preprocessed images:
1. To black/white scale:
![image](https://github.com/user-attachments/assets/adbe52fe-7d35-49de-8a13-a9bd33b2b4da)  
2. Denoising:
![image](https://github.com/user-attachments/assets/930e8eb1-84a2-433f-8337-25a63b4fcc6e)  












