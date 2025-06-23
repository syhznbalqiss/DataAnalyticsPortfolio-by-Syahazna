# My Data Analytics Portfolio
Welcome! I'm Balqis and these are my portfolio projects:

# 1. London Bike Rides 🚲
**Tools used:** Python, Tableau | **🔗 GitHub Repository:** [London Bike Rides](https://github.com/syhznbalqiis/London-Bike-Rides) | **📈 Tableau Dashbard:** [London Bike Rides Visualizations](https://public.tableau.com/views/LondonBikeRidesProject_17448649553330/Dashboard1?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

### Overview 👀

### Dataset 📂
- **Source:** https://www.kaggle.com/datasets/hmavrodiev/london-bike-sharing-dataset?resource=download 
- **Description:** The data is acquired from 3 sources:
  - Https://cycling.data.tfl.gov.uk/ 'Contains OS data © Crown copyright and database rights 2016' and Geomni UK Map data © and database rights [2019] 'Powered by TfL Open Data'
  - freemeteo.com - weather data
  - https://www.gov.uk/bank-holidays
From 1/1/2015 to 31/12/2016
The data from cycling dataset is grouped by "Start time", this represent the count of new bike shares grouped by hour. The long duration shares are not taken in the count.
- **Cleaning Process:**


# 2. Indonesia Tourism 🌴
**Tools used:** Python, Tableau | **🔗 GitHub Repository:** [Indonesia Tourism](https://github.com/syhznbalqiis/Indonesia-Tourism)

### Overview 👀


### Dataset 📂
- **Source:** https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination
- **Description:** There are 3 excel files used, namely
  - tourism_ with _id.csv which contains information on tourist attractions in 5 major cities in Indonesia totaling ~400
  - user.csv which contains dummy user data to make recommendation features based on user
  - tourism_rating.csv contains 3 columns, namely the user, the place, and the rating given, serves to create a recommendation system based on the rating
- **Cleaning Process:**
  - Some missing values are on tourism_with_id.csv, but since there are no information about the place name that associates with the place ID in other files so it's not possible to fill in the data
    ```python
    full_range = set(range(data1['Place_Id'].min(), data1['Place_Id'].max()+1))
    existing_range = set(data1['Place_Id']) 
    missing_values = sorted(full_range - existing_range)
    print("Missing place_id: ", missing_values)'
  - Removed some duplicates place ID in tourism_rating.csv
    ```python
    all_duplicates = data2[data2.duplicated(keep=False)]
    print("Duplicate rows: ", all_duplicates)
    duplicates = data2[data2.duplicated()]
    no_duplicates = data2.drop_duplicates()
    print("Without duplicates: \n", no_duplicates)
  - Dropped unused columns in both files such as, coordinate, longitude, latitude, and place ratings in the second file since the first file already has it.
    ```python
    data1 = data1.drop(['Coordinate', 'Lat', 'Long', 'Description'], axis=1)
    data2 = data2.drop(['Place_Ratings'], axis=1)

### Exploratory Data Analysis 📈
#### 📌 Key Findings
✔️ The dataset contains 8 columns and 10430 rows in total

✔️ No major missing values, but some data were duplicated

✔️ Freedom Library which is located in Jakarta is the highest ranked place, on the other hand, Saloka Theme Park in Central Java is the least ranked place made by the visitors

✔️ Yogyakarta is the most city that has tourist places

✔️ The Amusement Park category is the most in number in Yogyakarta

#### 📊 Summary Statistics

#### 📈 Trends and Visualization

