# global-IT-and-business-consulting-firm
a global IT and business consulting firm renowned for its expertise in IT solutions and highly experienced consultants. To stay competitive in the rapidly evolving technology landscape, thre organization regularly analyzes data to identify emerging and future skill requirements.

## Roles and responsibilities:
Contribute to this initiative by collecting data from diverse sources and identifying trends for this year's report on in-demand skills. One key source for analysis will be the latest Developer Survey, a comprehensive dataset offering insights into the global developer community.
iInitial task is to gather data on the most sought-after programming skills from various sources, including:

#### Job postings:

  - Training portals
  
  - Developer surveys, such as the latest Stack Overflow Developer Survey
  
  - Analyze it to identify key insights and trends. 

#### Trends: 

  - Which programming languages are most in demand?
  
  - Which database technologies are currently most sought after?
  
  - Which Integrated Development Environments (IDEs) are the most popular?
  

#### Working process:

  - Scraping internet websites, accessing APIs, and working with datasets like the latest Stack Overflow Developer Survey in various formats such as .csv files, Excel sheets, and databases.
  
  - Apply data-wrangling techniques to prepare the data for analysis.
  
  - Employ statistical techniques to analyze the data, identifying key trends and insights. 
  
  - Synthesize findings using IBM Cognos Analytics to create a dashboard that visualizes the results. 
  
  - Share insights through a presentation, showcasing your storytelling and data analysis skills.

# DATA PREPARE

## Scraping internet websites, accessing APIs, and working with datasets

### Collect Jobs Data using Job API
Collect the number of job postings for the following locations using the API: Los Angeles, New York, San Francisco, Washington DC, Seattle, Austin, Detroit

Objective: Determine the number of jobs currently open for various technologies and for various locations
```
#Import required libraries
import requests
import pandas as pd
import json
```

```
# Write a function to get the number of jobs for the Python technology.

api_url='https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DA0321EN-SkillsNetwork/labs/module%201/Accessing%20Data%20Using%20APIs/jobs.json'

# technology and location list
technologies = ['C', 'C#', 'C++', 'Java', 'JavaScript', 'Python', 'Scala', 'Oracle', 'SQL', 'MySQL', 'PostgreSQL', 'MongoDB']
locations = ['Los Angeles', 'New York', 'San Francisco', 'Washington DC', 'Seattle', 'Austin', 'Detroit']

def get_number_of_jobs_T(technology, location):
    # send request to API and get data
    response = requests.get(api_url)
    # check error
    if response.status_code != 200:
        print (f' error fetching data for {technology} in {location}')
        return (technology, location, 0) 
    # convert data to Json
    jobs_data = response.json()
    # count the technology job in each location
    number_of_jobs = sum( 1 for job in jobs_data if technology.lower() in job['Key Skills'].lower() and location.lower() in job['Location'].lower())
    return (technology, location, number_of_jobs)

# create the list for result
results = [get_number_of_jobs_T(tech, loc) for tech in technologies for loc in locations]

# convert list to data frame
df = pd.DataFrame(results, columns=['Technology', 'Location', 'Number of Jobs'])

# save the data to excel file
df.to_excel('D:/project/project_IT/job-postings.xlsx', index = False)
print(f' File saved ')

df.head(10)

````
