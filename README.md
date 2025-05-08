# Airline Passenger Satisfaction ✈

## 1. Business Understanding
This project analyzes feedback from over 120,000 airline passengers, including details about each person, their flight, and type of travel, along with their ratings on things like cleanliness, comfort, service, and overall experience. Understanding this is crucial for improving airline services, identifying what passengers value most, and making decisions that enhance customer satisfaction and overall travel experience.

### Scenario:
An airline company has been receiving mixed reviews from its passengers. A recent survey revealed that many customers reported dissatisfaction with delays, seat comfort, and in-flight service. 
With increased competition in the airline industry, the company is under pressure to improve its customer satisfaction scores to retain loyal customers and attract new ones. The company’s leadership team wants to develop a new strategy to enhance the overall passenger experience, based on real feedback and data.

### Business Question:
What strategies should the airline company use to improve customer satisfaction, based on passenger feedback and service data?

## 2. Data Lifecycle
The data in this project follows a standard lifecycle:

1. **Business Problem**:
    An airline company wants to improve its customer satisfaction scores to retain loyal customers and attract new ones.
2. Data Collection:
   Raw data is generated from a survey, stored in a CSV file.
3. **Data Processing**:
   - Ensuring the data is accurate.
   - Remove duplicate values.
   - Handle missing values, and correct errors (e.g., misspellings or inconsistent categories like “Economy” vs “economy”).
4. **Data Analysis**:
   Applying statistical and analytical techniques to extract insights.
   - Identifying customer satisfaction for each category.
   - Using Python to calculate the average, minimum, maximum, and percentage.
   - Creating visual summaries with Excel (e.g., pivot tables, bar charts) to illustrate trends.
5. **Data Presentation**:
   Communicating findings through visualizations, reports to inform decision-making, and giving recommendations.
   - Creating dashboards to show and demonstrate the insights found during the analysis.

<img width="502" alt="Data_life_cycle" src="https://github.com/user-attachments/assets/c4a97299-7b45-48d8-8b01-50e123296f2a" />

## 3. Methodology
Excel and Python were utilized for this analysis.

## 4.1. Excel Analysis:
The following tasks were performed in Excel using the `airline_passenger_satisfaction.csv` file:

1. **Data Import**: The CSV file was loaded into Excel.
2. **Aggregation**: 
    - Identify the total number of `customers` by gender using the `CountIf` formula: `=COUNTIF(B2:B129881,"Male")` and `=COUNTIF(B2:B129881,"Female")`.
    - Identify the total number of `Returning customers` and `First-time customers` using the `CountIf` formula: `=COUNTIF(D2:D129881,"Returning")` and `=COUNTIF(D2:D129881,"First-time")`
3. **Pivot Table**:
   - Pivot Tables were generated from the data:
   - To count the satisfaction points for each type of customer based on the `Food and Drink` ratings
   - To count the satisfaction points for each type of customer based on `Ease of Online Booking` and `Check-in Service` ratings.
   - To count the satisfaction points for each type of customer based on `On-board Service`, ` Baggage Handling`, `In-flight Wifi Service`, `In-flight Entertainment`, and `Cleanliness` rating.
  
     <img width="903" alt="Screenshot 2025-05-08 at 10 58 08 AM" src="https://github.com/user-attachments/assets/209cc349-b547-4096-a817-af38ccabcd19" />

4. **Pivot Charts & Visualization**:
   - Three Pivot Charts (specifically a bar chart and a pie chart) were created from the Pivot Table:
   - to show the customer satisfaction per seat comfort

     <img width="637" alt="Screenshot 2025-05-08 at 11 05 29 AM" src="https://github.com/user-attachments/assets/56345ef4-b9f0-43e8-b6ee-1352bee81862" />

   - The Arrival and Departure delays:
  
    <img width="695" alt="Screenshot 2025-05-08 at 12 59 18 PM" src="https://github.com/user-attachments/assets/d03c0b93-7f88-43a5-a590-383d960ed0c4" />


   - The percentage of customer satisfaction per class
  
     <img width="485" alt="Screenshot 2025-05-08 at 11 11 38 AM" src="https://github.com/user-attachments/assets/26eca7fa-7e30-488e-908a-a0f1c00d3d05" />

## 4.2. Python Analysis:
In Python, I used the `Pandas` library to perform some tasks:
1. **Data Loading:**
   - Import the `pandas` module to open and read the dataset: `import pandas as pd `
2. **Data Exploration:**
   - Print the header row (column names) of the dataset using `print(df.keys())`:
     `Index(['ID', 'Gender', 'Age', 'Customer Type', 'Type of Travel', 'Class',
       'Flight Distance', 'Departure Delay', 'Arrival Delay',
       'Departure and Arrival Time Convenience', 'Ease of Online Booking',
       'Check-in Service', 'Online Boarding', 'Gate Location',
       'On-board Service', 'Seat Comfort', 'Leg Room Service', 'Cleanliness',
       'Food and Drink', 'In-flight Service', 'In-flight Wifi Service',
       'In-flight Entertainment', 'Baggage Handling', 'Satisfaction'],
      dtype='object')`
3. **Agregation:**
   - Descriptive statistics: using the `.describe()` method on the dataframe to calculate average, minimum, maximum, and percentage. ` ID            Age  Flight Distance  Departure Delay  \
count  129880.000000  129880.000000    129880.000000    129880.000000   
mean    64940.500000      39.427957      1190.316392        14.713713   
std     37493.270818      15.119360       997.452477        38.071126   
min         1.000000       7.000000        31.000000         0.000000   
25%     32470.750000      27.000000       414.000000         0.000000   
50%     64940.500000      40.000000       844.000000         0.000000   
75%     97410.250000      51.000000      1744.000000        12.000000   
max    129880.000000      85.000000      4983.000000      1592.000000 `

4. **Filter Data:**
   - I wrote a basic loop to filter rows based on a specific condition.
         - `filter = df["Customer Type"] == "Returning"` return `returning customers` rows from the dataframe.
5. **Summary:** The Python script helps with loading a big dataset, cleaning it and ensuring the data is clean for further analysis.


## 5.  Data Types:
The dataset `airline_passenger_satisfaction.csv` comprises 129,880 records and 24 columns. These columns reveal the following data type:
1. **Qualitative Data**: This form of data describes and helps us understand why, how, or what happened behind certain behaviors.
Example: `Customer Type`, `Type of Travel`, `In-flight Wifi Service`, `Cleanliness`, `Seat Comfort`
2. **Quantitative Data:** This form of data tells us how many, how much, or how often in calculations. Example: `Flight Distance`, `Departure Delay`, `ID`, `Age`.

   **Full list of columns in the dataset:**`['ID', 'Gender', 'Age', 'Customer Type', 'Type of Travel', 'Class',
       'Flight Distance', 'Departure Delay', 'Arrival Delay',
       'Departure and Arrival Time Convenience', 'Ease of Online Booking',
       'Check-in Service', 'Online Boarding', 'Gate Location',
       'On-board Service', 'Seat Comfort', 'Leg Room Service', 'Cleanliness',
       'Food and Drink', 'In-flight Service', 'In-flight Wifi Service',
       'In-flight Entertainment', 'Baggage Handling', 'Satisfaction']`


## 6. Three Keys Learning:
1. **Problem Statement:** Defining the problem statement is very important because it helps respond to the following question:
   - What is the problem you wanna solve?
   - Also, guide the data-driven process.
  
2. **Data Cleaning:** Data cleaning is a very important step because it ensures the data is clean and free of errors and helps to manipulate the data for further analysis.

3. **Communicate Insights:** Demonstrating insights we found by doing some visualization and creating a Dashboard is very important to communicate effectively with team members. It helps to better understand the problem and take action.
     
## 7. Summary and Business Recommendations:
- Online booking: difficulty booking a flight online for new customers.
- On-board service: more customers are dissatisfied, especially for the first customer who flies in economy class.
- Baggage handling: More people are dissatisfied with that service. Specially for the first customer.
- More people are satisfied with in-flight wifi services, entertainment, and the cleanliness service.
- In-Flight Service, Baggage Handling, and Seat Comfort are the best 3 Rating Services from Passengers.
- Wifi, Ease of Online Booking, and Gate Location services got poor ratings from Passengers.

  To Improve Customer Satisfaction, The Airline company:
  - Improve punctuality by minimizing delays and communicating clearly when they happen.
  - Enhance in-flight experience: offer better food, entertainment, Wi-Fi, and seating comfort.
  - Train staff should be focused and friendly, and provide efficient service from booking to baggage claim.
  - Reward frequent flyers with perks like upgrades, early boarding, or lounge access.
  - Handle complaints quickly by responding promptly to issues and offering compensation when appropriate.








