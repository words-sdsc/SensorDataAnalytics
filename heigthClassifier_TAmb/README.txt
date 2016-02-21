Read Ambient Temperature to predict node's position (Top/Bottom)

Python reads sensor generated data to extract Tamb time series - one per sensor (each row=a sensor).Python prints the file names in order. This is used to get ClassId for each row. Python writes to file
"eachRowTimeSeries.txt"

R reads the time series data generate by Python. R uses Discrete Wavelet Transform (DWT) with Haar filter to get DWT coefficients for each time series, and write to a file 'dwtFeatures_TAmb.csv'
ClassId are appended to each row in R. The labels are added in R using the order inwhich Python generate the input file 'eachRowTimeSeries.txt'.

Python reads dwt features ('dwtFeatures_TAmb.csv') and builds a Random Forest Classifier. The DWT coefficients of the time series sensor data are used a features. The dataset ('dwtFeatures_TAmb.csv') is split randomly into 
training and test set. 
