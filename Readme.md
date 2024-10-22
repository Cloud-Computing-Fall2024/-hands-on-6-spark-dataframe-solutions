
---

## **Hands-on: Spark SQL and DataFrames**

### **Objective:**
In this activity, you will learn how to use **Spark DataFrames** and **Spark SQL** to perform complex data analysis. You will work with a dataset containing historical weather data. The goal is to get hands-on experience using DataFrame transformations and SQL queries to derive meaningful insights from the dataset.

### **Dataset:**
The dataset contains historical weather data. Each record represents daily weather information, including temperature, precipitation, and wind speed for a specific location and date.

### **Dataset Columns:**
- **Date**: Date of the weather observation.
- **Location**: Name of the city or location.
- **MaxTemp**: Maximum temperature recorded on that day.
- **MinTemp**: Minimum temperature recorded on that day.
- **Precipitation**: Amount of rainfall or snowfall (in mm).
- **WindSpeed**: Average wind speed (in km/h).
- **WeatherCondition**: Description of the weather (Sunny, Rainy, Snowy, Cloudy, etc.).

---

### **Tasks:**

#### **Task 1: Descriptive Statistics for Weather Conditions (Use Spark SQL)**
- **Objective**: Use Spark SQL to calculate basic descriptive statistics for the weather data.
- **Instructions**:
  - Register the weather_df DataFrame as a temporary SQL table.
  - Write a SQL query to calculate:
    - Average, minimum, and maximum temperature (both MaxTemp and MinTemp) for each location.
    - Average precipitation and wind speed for each location.
  - Sort the results by the average temperature in descending order.
- **Expected Outcome**: A DataFrame that shows each location with its average temperature, precipitation, wind speed, and sorted by the hottest locations.
- **Hint**: Use SQL queries like SELECT, GROUP BY, AVG(), MIN(), MAX(), and ORDER BY to achieve this task.

#### **Task 2: Identifying Extreme Weather Events**
- **Objective**: Identify locations that experienced extreme weather events.
- **Instructions**:
  - Define extreme weather as:
    - MaxTemp > 40°C or MinTemp < -10°C.
    - Precipitation > 50 mm.
    - WindSpeed > 50 km/h.
  - Create a DataFrame that lists the locations and dates where these extreme weather conditions were recorded.
  - Count the number of extreme weather events for each location.
- **Expected Outcome**: A list of locations and dates where extreme weather conditions were recorded and a count of extreme events per location.

#### **Task 3: Analyzing Weather Trends Over Time**
- **Objective**: Analyze how weather conditions change over time at specific locations.
- **Instructions**:
  - Select two or three cities from the dataset.
  - For each city, calculate the monthly average **MaxTemp**, **MinTemp**, and **Precipitation**.
  - Plot the trend of these values over time using Spark’s DataFrame API (or exporting to a library like `matplotlib` for visualization).
- **Expected Outcome**: Monthly weather trends for each city, showing temperature and precipitation changes over the months.

#### **Task 4: Finding the Best and Worst Days for Outdoor Activities**
- **Objective**: Use Spark SQL and DataFrames to determine the best and worst days for outdoor activities.
- **Instructions**:
  - Define “best days” for outdoor activities as:
    - MaxTemp between 20°C and 30°C.
    - Precipitation < 5 mm.
    - WindSpeed < 15 km/h.
  - Define “worst days” as days with:
    - MaxTemp < 0°C or > 35°C.
    - Precipitation > 30 mm.
    - WindSpeed > 40 km/h.
  - Create two DataFrames: one listing the best days for outdoor activities and the other for the worst days.
- **Expected Outcome**: Two DataFrames, one with the best days and the other with the worst days for outdoor activities.

---

### Detailed Instructions for Students: How to Install PySpark and Run Jobs Using `spark-submit`

1. **Loading the Data**: The weather dataset will be provided as a CSV file. Load the data into a Spark DataFrame using:
   ```python
   weather_df = spark.read.csv('weather_data.csv', header=True, inferSchema=True)
   ```

2. **Performing the Tasks**: Complete the four tasks using Spark SQL or DataFrame transformations.


In this hands-on activity, you will be working with **PySpark** to analyze the weather dataset using Spark SQL and DataFrames. The following steps will guide you on how to install **PySpark** and run your Spark job using the `spark-submit` command.

---

### **Step 1: Install PySpark Using pip**

Since you will be working in GitHub Codespaces, **Java and Python are already installed**, but we need to install **PySpark**. You can do this using `pip`.

1. Open the terminal in **GitHub Codespaces**.

2. Run the following command to install PySpark:

   ```bash
   pip install pyspark
   ```

3. After the installation is complete, verify that PySpark is installed by running:

   ```bash
   python -c "import pyspark; print(pyspark.__version__)"
   ```

   This should display the version of PySpark that you have installed.

---

### **Step 2: Write Your Spark Job in Python**

Make sure that you have your Python script ready for the Spark job. If you are following along with the provided activity, you should have a Python file (for example, `weather_analysis.py`).


Make sure you have your Python script saved in your working directory (for example, `weather_analysis.py`).

---

### **Step 3: Running the Spark Job Using `spark-submit`**

Now that you have PySpark installed and your Python script ready, you can run your Spark job using the `spark-submit` command.

1. Ensure you are in the directory where your Python script (e.g., `weather_analysis.py`) and the dataset (e.g., `weather_data.csv`) are located.

2. Run the Spark job using `spark-submit`:

   ```bash
   spark-submit weather_analysis.py
   ```

This will start Spark and run your Python script on the Spark cluster. You will see the logs in your terminal, and the output of your Spark job will be displayed as well.

---

### **Step 4: Viewing the Output**

Once the job completes, the output will be shown directly in the terminal. Depending on your script, you may see DataFrame results, statistics, or any logs generated by the job.

For example, if you have a DataFrame with a `.show()` method, you should see the first few rows of the DataFrame in the terminal.

---

### **Troubleshooting:**
- If the Spark job fails to run, check for errors in the logs, such as:
  - **Missing files**: Ensure the dataset (`weather_data.csv`) is in the correct directory.
  - **Syntax errors**: Review your Python script for any typos or issues in the code.

---

### **Final Notes:**

- Make sure that both your Python script and dataset are in the same directory before running the `spark-submit` command.
- This activity will be completed entirely in **GitHub Codespaces**, so there's no need to install additional dependencies like Java.


**Submission**: Submit your Python notebook (or `.py` script) with the results of each task clearly displayed. You should include comments in your code explaining your approach.

**Single Page Report**: Submit a single page report on canvas describing the procedure that you have followed to finish this hand-on.

Good luck, and if you encounter any issues, feel free to reach out during the class or on the course forum!


### **Grading Criteria**:

- **Correctness**: Each task should be implemented correctly with accurate results.
- **Code Clarity**: The code should be well-structured, with meaningful variable names and comments.
- **Optimization**: Use Spark’s functions and transformations efficiently.
- **Analysis and Insights**: Explain your results, especially for trends and weather analysis.

---