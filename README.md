# Men-s-T20-Cricket-Runs-Predictor

### Goal: A streamlit web app that predicts the first innings runs scored by a team taking the runs of the first five overs as input.

### Data set: 
The data set is downloaded from [Kaggle](https://www.kaggle.com/veeralakrishna/cricsheet-a-retrosheet-for-cricket?select=t20s).
The data is provided in YAML format, a human-readable data format.
The data is provided in a number of zip files, one of which contains all of the matches, and the others certain sub-sets of matches,
such as for the type of matches, matches for certain countries, teams, or genders, or periods of time.

### Project Brief:
The project is divided into four main parts:
1. Data Extraction: In this step, I have extracted the data from the yaml files and convert into a dataframe so that the machine learning model can use this data and predict the runs of the first innings.
2. Feature Engineering: This is the most challenging part of the project. Ball by ball data was extracted from the "innings" feature.
Top 10 teams were selected, city was extracted from venue and only those cities were considered in which 600+ balls were bowled.
Apart from these, lot of other feature engineering techniques were applied and important features were selected.
3. Model Building: Scikit-Learn's pipeline was used to make the code reusable. XgBoost Regressor was trained on the selected features
after testing with various other regression algorithms. Model was evaluated on the test data set in terms of R2 score. 
Model performed really well with slight amount of hyper parameter tuning giving an R2 score of 0.987 and Mean Absolute Error of 1.67
which is pretty much good.
4. Model Deployment: Finally, the model was deployed on local server (port:8501) using Streamlit.

### Demo:
![image](https://user-images.githubusercontent.com/75041273/137994959-58497f32-a796-43f2-9aa2-9eb1c3d8de04.png)

### Installation:
The Code is written in Python 3.7.3 If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:

##### 1. First create a virtual environment by using this command:
```bash
conda create -n myenv python=3.7
```
##### 2. Activate the environment using the below command:
```bash
conda activate myenv
```
##### 3. Then install all the packages by using the following command
```bash
pip install -r requirements.txt
```
##### 4. Download the model files from [here](https://drive.google.com/drive/folders/17KxvKpPHvHmrfdOyJClU0o95JTDAAG60?usp=sharing) and put it in the same working directory.


##### 5. Then, in cmd or Anaconda prompt write the following code:
```bash
streamlit run app.py
```

##### Make sure to change the directory to the root folder. The folder structure should be same as of this repository otherwise it will throw error. 

