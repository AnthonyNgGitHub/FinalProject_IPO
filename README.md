# Group Project - IPO Analysis
UofT Data Analytics - Module 20: Final Project

---

## Contents 
  * Overview
    - Purpose
    - Resources
    - Communications
    - Team Member
  * Results
  * Summary
 

---  
   ### Purpose
   To apply machine learning and neural networks and use the features within our provided dataset to create a binary classifier that is capable of predicting upcoming IPO returns by industry/sector. 
  
   - Deliverable 1: Presentation
   - Deliverable 2: GitHub
   - Deliverable 3: Machine Learning Model
   - Deliverable 4: Database
   - Deliverable 5: Dashboard 
  
   ### Resources
   * Data Resources
     1. IPOScoop:  https://www.iposcoop.com/
     2. Alpha Vantage: https://www.alphavantage.co/documentation/
  
  * Software/Tools: Python, Pandas, Visual Studio Code, PostgreSQL, Jupyter Notebook, Tableau,
  * Languages: Python
  * Algorithm: Neural Network
  
  ### Communications
  1. Slack Channel
  2. Github Collaboration 
  3. Zoom Meeting
  
  
  ### Team Member:
 * Andrew Sukmawan
 * Anthony Ng
 * Lora Borja
 * Reina Lim
  

## Results

## Presentation

   | Selected Topic   |  IPO Analysis  | 
   | :--- | :--- |
   | **Reason why this topic was selected** | 1. Personal interest <br/> 2. Availability of data source <br/> 3. Discover how the global pandemic affected IPO listing |
   | **Questions hoping to answer** | 1. What is the proportion of each sector? <br/> 2.Which industries have the best and worst return in 2019 and 2020? <br/> 3. How has the appetite for IPOs in each sector changed? How did they performed over the years from 2000 to 2020? <br/> 4. How can you benefit from the above information?
   | **Data Source** | IPOScoop: https://www.iposcoop.com/ <br/> Alpha Vantage: https://www.alphavantage.co/documentation/ <br/><a href="https://github.com/reinalim/FinalProject_IPO/tree/Develop/DataExtraction"> **Click here to learn more about data extraction** </a> 
   
   <a href="https://docs.google.com/presentation/d/1ZlcIOSct6o92qZ16Grknb6WAb4lZjYQNEJHsQfV6WdI/edit?usp=sharing" target="_blank"> **Link to Google Slides** </a>
  
  ## GitHub  
   
   Master Branch 
   * All code necessary to perform exploratory analysis - Completed
   * Some code to complete the machine learning portion of the porject - Completed 
   
   README.md
   * Description of the communication protocols - Established
   * Outline of the project - Completed
   * 18 Commits in total - Completed
   
  ## Machine Learning Model

  #### Model Choices

  #### Training/Testing Split

- During Training/Testing our models, the highest accuracy found for both Three Month Return and First Day Closing Price was found when using a 67% training and 33% testing split

 #### Model Selection

- Since we have labeled data, we've tried using a variety of different binary classification models:
    - Logistic Regression
<img src="https://github.com/reinalim/FinalProject_IPO/blob/Develop/ML_Model/images/log.png" width="80%">

   - Random Forest
<img src="https://github.com/reinalim/FinalProject_IPO/blob/Develop/ML_Model/images/random.png" width="80%">

   - Deep Learning
    - Using all our 10 features, our models performed:
        - **Three Month Return model: Current Accuracy 71%**
        - **First Day Closing Price model: Current Accuracy 65%**
       
<a href="https://github.com/reinalim/FinalProject_IPO/tree/Develop/ML_Model"> **Click here for learn more about Machine Learning Model Choices** </a>
     
## Database
   
   **Entity Relationship Diagram (ERD)** - Showing Relationships
   
   - List of Tables:
   
   	- Three Month Return 
	- Income Statement
	- IPO Scoop Listing
	- Company Overview
	- Cash Flow Statement
	- Balance Sheet

  <img src="https://github.com/reinalim/FinalProject_IPO/blob/Develop/SQL/FinalProject_IPO_ERD.png" width="80%">

<a href="https://github.com/reinalim/FinalProject_IPO/tree/Develop/SQL"> **Click here to learn more about database details** </a>

## Dashboard
   
  **Description of the tool**
   
  <img src="https://github.com/reinalim/FinalProject_IPO/blob/Develop/Dashboard/Images/Tableau%20Logo.png" width="50%">
  
  Tableau is a data visualization software that is used for data science and business intelligence. Tableau can create a wide range of different visualization to interactively present the data and showcase insights.
 
 **Dashboard Overview**
 
Part #1
<img src="https://github.com/reinalim/FinalProject_IPO/blob/Sub-branch/Dashboard/Dashboard/Images/Dashboard_Tableau.png" width="100%">

Part #2: Machine Learning Visual
<img src="https://github.com/reinalim/FinalProject_IPO/blob/Develop/Dashboard/Images/Dashboard_Table2.png" width="100%">

<a href="https://github.com/reinalim/FinalProject_IPO/tree/Develop/Dashboard"> **Dashboard Workflow Details** </a>

  **Description of interative element(s)**
   - Search and Filter Functions available on Tableau Dashboard <a href="https://public.tableau.com/profile/reina6848#!/vizhome/Book1_16172235019440/DashboardFinal1?publish=yes"> **Link to Tableau Dashboard** </a>

<br>

**For presentation, please click the link below:**
   <a href="https://docs.google.com/presentation/d/1ZlcIOSct6o92qZ16Grknb6WAb4lZjYQNEJHsQfV6WdI/edit?usp=sharing" target="_blank"> Link to Google Slides </a>
<br>

---

## Analysis Results Recap
* Stock market’s appetite for IPOs is not affected by the recent economic downturn in 2020.
* First Day Returns are positively correlated with Gross Profit Margin while negatively correlated with Cash Flow from Investment (The higher the investment spent, the stronger the First Day Return).
* 3 Month Returns are positively correlated with EBITDA.
* Indeed, Gross Profit Margin, Cash Flow from Investment, and EBITDA turned out to be the most important features in our models, which returned an accuracy of 65% and 71% respectively.
* Our models were better at predicting Gains than Losses, as Gains had better precision and recall scores than Losses, for both the First Day Return and Three-Month Return.

---

## Recommendation for Future Analysis

#### To obtain data with higher quality:
* The extent of our analysis is partly limited by the quality and incompleteness of our data as we were only able to obtain sufficient quarterly financial information from Alpha Vantage  for 15%  of the original listing of IPOs.
* Therefore, there were not enough high quality data to perform meaningful statistical analysis to uncover trends in the relationship between Returns and various financial metrics.

