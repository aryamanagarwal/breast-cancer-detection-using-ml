# breast-cancer-detection-using-ml
Detecting Breast Cancer using Standard Vector Machine and K Nearest Neighbor models
The dataset used has been imported from : https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/breast-cancer-wisconsin.data<br>
A total of 11 columns exist in the dataset namely :
1. id                         int64
2. clump_thickness            int64
3. uniform_cell_size          int64
4. uniform_cell_shape         int64
5. marginal_adhesion          int64
6. single_epithelial_size     int64
7. bare_nuclei               object
8. band_chromatin             int64
9. normal_nucleoli            int64
10. mitoses                    int64
11. class                      int64<br>
Out of this 'id' column does not have any corelation with the classification so it has been removed
Also column 'bare_nuclei' was left out while training the model due to lot of missing values.
<br>
The column 'class' is indicative of whether the person has cancerous cell or not, class = 2 implies beningn(not cancerous) and class = 4 implies malignant (cancerous).
<br>
After that we divide the dataframe into X and Y. X containing the 8 attributes taken into consideration and Y containg the class value.<br>
After this we split the data into training and testing set.<br>
After this we evaulate the models(SVM,KNN) on training data using KFold and measuring the score using accuracy.<br>
On evaluation accuracy obtained were:<br> 
1. KNN: 0.964286 
2. SVM: 0.953571<br>
After this the model was trained on the training data and the predictions were made on the testing data.
Following accuracy score and classifiaction report was obtained.(Results might slightly vary on different runs.)<br>
KNN
0.9642857142857143
              precision    recall  f1-score   support

           2       0.99      0.96      0.97        90
           4       0.92      0.98      0.95        50

    accuracy                           0.96       140
   macro avg       0.96      0.97      0.96       140
weighted avg       0.97      0.96      0.96       140
The recall value of 0.96 tells that out of the total pateints classified as bening, 4% infact had malignant cancerous cell.
The precision value of 0.92 tells us that out of the total malignant predictions made only 92% were true.

SVM
0.95
              precision    recall  f1-score   support

           2       1.00      0.92      0.96        90
           4       0.88      1.00      0.93        50

    accuracy                           0.95       140
   macro avg       0.94      0.96      0.95       140
weighted avg       0.96      0.95      0.95       140
The recall value of 0.92 tells that out of the total pateints classified as bening 8% infact had malignant cancerous cell.
The precision value of 0.88 tells us that out of the total malignant predictions made only 88% were true.
