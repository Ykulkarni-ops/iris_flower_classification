# Iris Flower classification using JSON

## Project pipeline
- For Iris flower classification I have used google colab. I have uploaded the zip file to google drive and made some changes to the namings to make the files usable with ease. 
- **Step 1**:
    - The first step in this project was to retrive the JSON data through an rtf file. 
    - I have used library striprtf to convert the rtf file to plain text file and then converted the plain text file to JSON. 
    - Once the file is converted to JSON I have used "json" library in python to parse the JSON data. 
    - The sample of parsed JSON data is given below:</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/parsed_json.png" width = 700  title ="parsed_json" /></br>
- **Step 2**: 
    - The second step is to read the target and the regression type. 
    - To read the target and regression type I have created a function "parse_target_and_regression". 
    - This function gets the target from target_data = json_data["design_state_data"]["target"] and then logs the target and type to the console.</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/target_type.png" width = 700  title ="parsed_json" /></br>
- **Step 3**: 
    - In this step I have to perform feature handling on the parsed JSON data. 
    - Here I have retrived the values of imputation method and imputation value. 
    - The two main methods used are "Average of values" and "Custom". 
    - The function "parse_and_impute_data" helps with the feature handling. 
    - The output for feature handling is given below.</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/feature_handling.png" width = 700  title ="parsed_json" /></br>
- **Step 4**: 
    - This step includes feture reduction. 
    - The method mentioned in the JSON is Tree-based reduction. 
    - I have also made sure that the feature reduction runs if the reduction method is changed to No reduction, Corr with Target or PCA. 
    - The function "feature_reduction" helps with the above. 
    - The output for feature reduction is given below</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/feature_reduction.png" width = 700  title ="parsed_json" /></br>
- **Step 5**: 
    - The next step was to create the models based on the prediction type. 
    - Here the prediction type was given as regression. 
    - I have also considered models for which the is_selected is False. 
    - The function "create_models" helps to create the models. 
    - The output for the models is given below.</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/model_created.png" width = 700  title ="parsed_json" /></br>
- **Step 6**: 
    - I had to perform fit and predict on all the models. 
    - For this to work I needed to parse the hyperparameters for each model and convert them to the sckit learn params used in GridSerchCV. 
    - Hence, I created a function that maps the hyperparameters for each regression model to sklearn parameters. 
    - The output for is given below.</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/param_grid.png" width = 700  title ="parsed_json" /></br>
- **Step 7**: 
    - In this step I created a function "fit_and_predict" to run the GridSearchCV to fit and predict all the models and do hyperparameter tuning as well. 
    - The function runs all models and finds the metrics for Mean Squared Error (MSE) and R2 score. 
    - After all models are executed, it find the best model, best metrics and best hyperparameters, which are logged to the console.
    - The output is given below.</br>
<img src = "https://github.com/Ykulkarni-ops/iris_flower_classification/blob/main/images/grid_search.png" width = 700  title ="parsed_json" /></br>

## Dependancies 
- json==2.0.9
- striprtf==0.0.27
- logging==0.5.1.2
- pandas==2.2.2
- numpy==1.26.4
- scikit-learn==1.5.2

## Instructions 
- The code is dynamic in nature. 
- To load the csv file for running the function in the notebook, replace the variable "csv_path" with actual file path. 
- Also, any changes made to JSON data such as changing the "is_selected" feature to true will not have any issues. 

## Author
[Yash Kulkarni](https://github.com/Ykulkarni-ops)
